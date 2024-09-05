When working out a architecture for a new project the following artefacts/steps are helpful:

1. **Understanding the domain & core use cases.**
	1. Requirements should be sorted by priority.
	2. Make a short list of critical path features that are a MUST for an MVP
	3. Make sure the client understands MVP (minimum viable product), MMP (minimum marketable product), MLP (minimum lovable product), ... and you and they are on board with an approach to the development.
2. Draw a data flow diagram that shows the interactions between the user and all required systems for the core use cases.
3. Draw a domain model to establish a vocabulary that can be used with the client. This also ensures that you've understood the problem domain correctly and that you can communicate with stakeholders effectively. Base the domain model upon the data flow diagram and verify that they are in sync. When deviations appear make sure to rectify them in all existing artefacts.
4. Draw a high level system diagram that shows all the required systems. Try to find matching technologies for the needed systems. E.g. database -> RDBMS vs. NoSQL. Cloud vs OnPrem etc.

It is also important to keep in mind that in the real world there are often many constraints that restrict your freedom when choosing a software architecture. Often times a client already has existing applications, internal developers with specific skillsets & preferences, business relationships with vendors such as microsoft, google or oracle and so on. These constraints reduce the freedom to choose just any technology or architecture pattern. Of course it is still important to consider options that are different from what a client is used to. But when going such a route they do require more convincing and good arguments.