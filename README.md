# ByteScout-Document-Parser-SDK-C-General-Example
ByteScout Document Parser SDK – C# – General Example

```
using System;
using ByteScout.DocumentParser;
// This example demonstrates document data parsing to JSON and YAML formats.
namespace GeneralExample
{
    class Program
    {
        static void Main(string[] args)
        {
            string inputDocument1 = @".\DigitalOcean.pdf";
            string inputDocument2 = @".\AmazonAWS.pdf";

            // Create DocumentParser instance
            using (DocumentParser documentParser = new DocumentParser("demo", "demo"))
            {
                Console.WriteLine($"Parsing \"{inputDocument1}\"...");
                Console.WriteLine();

                // Parse document data in JSON format
                string jsonString = documentParser.ParseDocument(inputDocument1, OutputFormat.JSON);
                // Display parsed data in console
                Console.WriteLine("Parsing results in JSON format:");
                Console.WriteLine();
                Console.WriteLine(jsonString);

                Console.WriteLine();
                Console.WriteLine($"Parsing \"{inputDocument2}\"...");
                Console.WriteLine();

                // Parse document data in YAML format
                string yamlString = documentParser.ParseDocument(inputDocument2, OutputFormat.YAML);
                // Display parsed data in console
                Console.WriteLine("Parsing results in YAML format:");
                Console.WriteLine();
                Console.WriteLine(yamlString);
            }

            Console.WriteLine();
            Console.WriteLine("Press any key to continue...");
            Console.ReadLine();
        }
    }
}
```
