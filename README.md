# Using Mermaid and ChatGPT to build technical diagrams 

## Table of Contents 

- [Getting Started](#getting-started)
- [Using ChatGPT to build Mermaid diagrams](#using-chatgpt-to-build-mermaid-diagrams)
- [Validating Mermaid diagrams built with ChatGPT outputs](#validating-mermaid-diagrams-built-with-chatgpt-outputs)
- [Putting your Mermaid diagram in your DITA map in Oxygen](#putting-a-mermaid-diagram-in-a-dita-map-in-oxygen)
- [Additional resources](#additional-resources)

## Getting Started 

1. Install this [Mermaid plugin](https://github.com/oxygenxml/dita-ot-diagrams-plugin) for your Oxygen instance
2. Read [this doc](https://blog.oxygenxml.com/topics/embedding_diagrams_in_dita_topics_using_mermaid.html) to learn more about the plugin and how to use the above plugin 
3. Open this [Mermaid diagram renderer](https://mermaid.live/edit#pako:eNpVjk1rhEAMhv9KyKmF9Q94KHS13ctCC92b4yFodIY6H4wZlkX97x3rpc0p4XnelyzY-Z6xxGHy905TFLjVykGe16bS0cxiaW6hKF7WCwtY7_ixwvnp4mHWPgTjxufDP-8SVMt11xhEG_e9Haj6zX84XqFurhTEh_Yvud39Cm-N-dS5_j_RkXPqvRmoHKjoKEJFscUTWo6WTJ9fX_aAQtFsWWGZ154HSpMoVG7LKiXxXw_XYSkx8QmjT6PG3DfN-UqhJ-Ha0BjJHsr2A4ifWns) to test your diagrams without having to do a lot of PDF builds 
4. Have ChatGPT open and ready
5. Have your developer diagram mockup (probably on Miro or Figma) open

## Using ChatGPT to build Mermaid diagrams 

Your prompts may vary based on the use case and the depth of complexity for your assigned diagram, but the key workflow should roughly stay the same. 

1. Export the developer mockup diagram as a png/jpeg 
2. Prompt ChatGPT to output Mermaid.JS code for a diagram based on the image of the diagram mockup (attach the image file to the prompt and tell it to use it as the knowledge source for the output)
3. Spot check the Mermaid ouput for any errors. Mermaid syntax is simple so spotting any glaring errors should be easy (more on this in the next section)

## Validating Mermaid diagrams built with ChatGPT outputs

ChatGPT is a great tool but it isn't always accurate. Still, if it gets you a 50-70% accurate first draft, then that is valuable. You'll be able to build diagrams faster than with Visio or other outdated tools. Mermaid diagrams may not be as pretty, but for the diagrams you work with, function is paramount to form. Thus, it is important to validate your diagrams in two ways—accuracy of visual output and accuracy of technical information. 

### Validating visual output 

To validate visual output, use the Mermaid live editor to build the code that ChatGPT gives you. Compare the diagram output to the developer mockup. There may be minor visual differences (ex. the output may be more simple than the mockup). If the diagram looks correct, share it with your engineering team to ensure that it meets their standards. If it does not, gather feedback and iterate. 

### Validating technical accuracy 

After sharing the AI-output Mermaid diagram with your engineering team for their feedback on the visual output, ask them to do a technical pass to ensure there were no AI hallucinations in the output. You'll likely catch major mistakes and hallucinations before you even share the diagram with engineers, but their additional feedback is needed. More reviewing eyes never hurts! If there are technical errors that exist that engineers call out, use that feedback to iterate until it's correct. 

## Putting a Mermaid diagram in a DITA map in Oxygen 

Once the Mermaid plugin is installed in your Oxygen instance, adding Mermaid code is simple. The plugin converts your Mermaid syntax into SVG diagrams once you export to PDF. An example of Mermaid syntax for a diagram in a Dita topic may look something like this:

```xml 
<topic id="MermaidDiagram">
    <title>Mermaid diagram example</title>
    <body>
        <p>
            <foreign outputclass="embed-mermaid-diagram">graph TD;
                A-->B;
                A-->D;
                B-->C;
                C-->D;</foreign>
        </p>
    </body>
</topic>
```
## Additional Resources 

- [Mermaid.JS docs](https://mermaid.js.org/)
- [Mermaid usage and best practices](https://mermaid.js.org/config/usage.html)
