# biome-parser

Best-effort parser for Apple Biome SEGB stream files.

This keeps the low-level SEGB record dumping and adds:

* Interval summary output for app usage, app focus, and Wi-Fi state
* Wi-Fi semantic event time fallback to the SEGB record timestamp

It also keeps schema-less protobuf wire decoding plus targeted semantic extraction for high-value pattern-of-life streams observed on current macOS systems:

* restricted/App.InFocus
* restricted/ScreenTime.AppUsage

## Important limitation:
    This is not an Apple-schema-aware parser. Apple does not publish the
    private protobuf schemas for Biome streams. The stream-specific fields
    below are inferred from record structure I've observed and should be
    validated against corroborating artifacts before report use.
