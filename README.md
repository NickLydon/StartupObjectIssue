# StartupObjectIssue
StartupObject not respected in csproj

[Following the getting started docs for the kafka dotnet client](https://developer.confluent.io/get-started/dotnet), the StartupObject node in the csproj is sometimes ignored.

Try alternating between `dotnet run --project consumer.csproj $(pwd)/getting-started.properties` and `dotnet run --project producer.csproj $(pwd)/getting-started.properties`.
The producer and consumer should each run in turn, but instead it repeatedly runs executes the previous one. The only way to get it to consistently run the chosen main method is to add the command line option `-p StartupObject=Consumer` or run `dotnet clean`.

`dotnet --version` is 6.0.100
