# Software Documentation Example with arc42 and C4 Model
This example shows how to use arc42 in combination with the C4 model with the Documentation as Code technique.

Tools: Structurizr DSL, Structurizr CLI & Asciidoctor

## Pre-Requisites

1. Install Asciidoctor, Asciidoctor diagrams and Asciidoctor pdf
2. Download the structurizr-cli into ./bin/structurizr-cli
3. Generate the diagrams from the structurizr workspace model

## Commands

### Generate PlantUML diagrams from C4 Model (Structurizr DSL)

``
./bin/structurizr-cli/structurizr.sh export -w bank.dsl -format plantuml/structurizr -output diagrams
``

### Generate HTML documentation with diagrams

``
asciidoctor -b html5 -r asciidoctor-diagram internet-banking-system.adoc
``

### Generate PDF documentation with diagrams

``
asciidoctor -b pdf -r asciidoctor-diagram -r asciidoctor-pdf  internet-banking-system.adoc
``