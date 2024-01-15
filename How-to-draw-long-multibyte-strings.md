There are workarounds to add long single-byte characters to the stack in GTA, but as for long multibyte strings, there aren't any workarounds.
I thought I needed to find how to draw long multibyte strings when I was making `Insane Stunt Bonus V` and trying to draw long Japanese texts.
Anyway, this is how to get sliced multibyte strings whose byte lengths are properly limited to 99 or less.
```
// in C#
public static string[] ToSlicedStrings(string input, int maxByteLengthPerString = 99)
{
    if (maxByteLengthPerString < 0)
    {
        throw new ArgumentOutOfRangeException("maxLengthPerString");
    }
    if (string.IsNullOrEmpty(input) || maxByteLengthPerString == 0)
    {
        return new string[0];
    }

    var utf8ByteCount = Encoding.UTF8.GetByteCount(input);
    if (utf8ByteCount <= maxByteLengthPerString )
    {
        return new string[] { input };
    }

    var initListCapacity = utf8ByteCount / maxByteLengthPerString;
    if (utf8ByteCount % maxByteLengthPerString > 0)
    {
        initListCapacity += 1;
    }

    var stringList = new List<string>(initListCapacity);
    var startIndex = 0;

    for (int i = 0; i < input.Length; i++)
    {
        var length = i - startIndex;
        if (Encoding.UTF8.GetByteCount(input.Substring(startIndex, length)) > maxByteLengthPerString)
        {
            stringList.Add(input.Substring(startIndex, length - 1));
            i -= 1;
            startIndex = (startIndex + length - 1);
        }
    }
    stringList.Add(input.Substring(startIndex, input.Length - startIndex));

    return stringList.ToArray();
}
// I'll change the method name if I find a better name or somebody tells me.
// Probably I can optimize performance of this method.
```
When you use some natives like `ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME` or `_BEGIN_TEXT_COMMAND_WIDTH`, you can use these strings by calling `_SET_TEXT_COMPONENT_FORMAT` with `CELL_EMAIL_BCON` and then calling those natives repeatedly with individual strings.
Yeah, I will post a workaround for C++, but I need to make one first.

EDIT: Fixed not slicing at a correct position.