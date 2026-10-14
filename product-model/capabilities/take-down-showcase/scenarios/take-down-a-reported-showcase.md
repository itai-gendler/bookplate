---
kind: primary
routes:
  cli: Server commands
steps:
  - text: The Server operator runs remove-showcase with the link that was reported
    kind: actor
    actor: server-operator
    entities:
      - { entity: showcase, effect: reads, facts: [Link] }
    contexts: { cli: { place: server-commands } }
  - text: The Product deletes the Showcase and says whose year it took down
    kind: product
    actor: server-operator
    entities:
      - { entity: showcase, effect: removes }
      - { entity: reader, effect: reads, facts: [Email] }
    contexts: { cli: { place: server-commands } }
---

# Take down a reported showcase

## Trigger

Someone reports a showcase to whoever runs the server.

## Outcome

The link stops working at once; the reader can make a new showcase.

## Edge cases

- Something that isn't a showcase link, or a showcase already off, is refused with a message.
