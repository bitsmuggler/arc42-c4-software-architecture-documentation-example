# Software Architecture Documentation Example with arc42 and C4 Model
This example shows how to use arc42 in combination with the C4 model with the Documentation as Code technique.

Technologies involved:

* [arc42](https://arc42.org/) to get the structure for the software architecture documentation
* [C4 Model](https://c4model.com/) an "abstraction-first" approach to diagramming software architecture, based upon abstractions that reflect how software architects and developers think about and build software.
* [Structurizr DSL](https://structurizr.com/dsl) to describe the [C4 Model](https://c4model.com/) of the software system
* [Structurizr CLI] (https://github.com/structurizr/cli) a command line utility for Structurizr to export the [PlantUML](https://plantuml.com/) diagrams from the C4 Model described in the Structurizr DSL
* [AsciiDoc](https://asciidoc.org/) as format to write the software architecture documentation
* [Asciidoctor](https://docs.asciidoctor.org/asciidoctor) to generate the representations of the software architecture documentation written in asciidoc 

## Prerequisites

* Install [Asciidoctor](https://docs.asciidoctor.org/asciidoctor), [Asciidoctor Diagrams](https://docs.asciidoctor.org/diagram-extension/latest/) and [Asciidoctor PDF](https://docs.asciidoctor.org/pdf-converter/latest/)
    * Asciidoctor: https://docs.asciidoctor.org/asciidoctor/latest/install/
    * Asciidoctor Diagrams: https://docs.asciidoctor.org/diagram-extension/latest/
    * Asciidoctor PDF: https://docs.asciidoctor.org/pdf-converter/latest/install/
* Download the [structurizr-cli](https://static.structurizr.com/download/structurizr-cli.zip), unzip and move it into ./bin/structurizr-cli
    * `curl --show-error --location https://static.structurizr.com/download/structurizr-cli.zip | tar -xf - -C bin/structurizr-cli`

## Generate the software architecture documentation representations

### Generate the diagrams from the structurizr workspace model

``
./bin/structurizr-cli/structurizr.sh export -w bank.dsl -format plantuml/structurizr -output diagrams
``

### Generate the documentation as HTML representation

``
asciidoctor -b html5 -r asciidoctor-diagram internet-banking-system.adoc
``

### Generate the documentation as PDF representation

``
asciidoctor -b pdf -r asciidoctor-diagram -r asciidoctor-pdf  internet-banking-system.adoc
``
