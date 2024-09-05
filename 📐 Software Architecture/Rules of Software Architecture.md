# 1st Law of Software Architecture: «Everything in architecture is a tradeoff»

If you think you’ve found something that isn’t a tradeoff, it just means you haven’t identified the tradeoff yet. There are no right or wrong answers in architecture; rather, it’s always about tradeoffs.

# 2nd Law of Software Architecture: «Why is more important than how»
Every architecture decision should be accompanied with a technical and business justification. Document decisions in [[Architectural Decision Records (ADR)]].

* **Structural design of software architecture**
	* Determine what architecture characteristics are present within the problem space.
	* Do logical component analysis to understand the problem domain.
* **As an architect, you should think about the artifacts within the architecture in terms of components**
	* Entity Trap: Do not consider every entity as a component, e.g. auction manager, item manager, bid manager. Instead consider workflows and identify actors.
* **Second Law of Software Architecture: «Why is more important than how»**
	* Every architecture decision should be accompanied with a technical and business justification
	* Document decisions in architectural decision records (ADRs)
	* [Examples](https://github.com/joelparkerhenderson/architecture-decision-record?tab=readme-ov-file)