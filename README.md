# Software Documentation Example with arc42 and C4 Model
This example shows how to use arc42 in combination with the C4 model with the Documentation as Code technique.

Tools: Structurizr DSL, Structurizr CLI & Asciidoctor

## Prerequisites

* Install [Asciidoctor](https://docs.asciidoctor.org/asciidoctor), [Asciidoctor Diagrams](https://docs.asciidoctor.org/diagram-extension/latest/) and [Asciidoctor PDF](https://docs.asciidoctor.org/pdf-converter/latest/)
    * Asciidoctor: https://docs.asciidoctor.org/asciidoctor/latest/install/
    * Asciidoctor Diagrams: https://docs.asciidoctor.org/diagram-extension/latest/
    * Asciidoctor PDF: https://docs.asciidoctor.org/pdf-converter/latest/install/
* Download the [structurizr-cli](https://static.structurizr.com/download/structurizr-cli.zip), unzip and move it into ./bin/structurizr-cli
    * `curl --show-error --location https://static.structurizr.com/download/structurizr-cli.zip | tar -xf - -C bin/structurizr-cli`

## Generate the documentation representation

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
