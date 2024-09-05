Code reviews are a collaborative process where developers examine and critique each other's code changes to improve quality, identify bugs, and share knowledge before the code is merged into the main branch. 

As an architect, code reviews are conducted to ensure that the implemented solutions align with the overall architectural vision, maintaining best practices and design patterns, while also facilitating knowledge sharing among team members.

# Strategy to review code as an architect

In order to continuously review code it’s useful to setup a branch, e.g. `review/backend-code-quality` that represents all the code you’ve reviewed. When getting started this can be just a copy of the `main` branch. Once the developers have merged new code into the `main` branch you can then open a merge request from `main` to  `review/backend-code-quality` in order to only review the new code.
The advantage of this strategy that it is fully decoupled from the normal development process and you aren’t blocking any developers.

## How to gather insights

The following points are worthwhile to periodically check for. They are ordered by importance. When doing a code review as an architect it’s important to timebox. E.g. limit your time investment to 2h for gathering insights.

- **Security**: Start with [[REST]] controllers and verify that all are restricted according to the specification. Ensure that it’s easy to understand what is accessible and by whom.
- **Layers**: Verify that code of the respective layers is in the correct package. E.g. controllers in the transport package.
- **Services:** Verify that it's clear what a service does and that it has a distinctive concern. Beware that’s it’s very time consuming and probably not worthwhile to check if it actually does the right thing. Checking the correctness of an implementation should be only done occasionally based on risk. Important stuff that will not get noticed in production, e.g. the calculation algorithm of a courtage should be double-checked by an architect. Otherwise you should trust your developers and their code review process for correctness.
- **Libraries:** Check if any new libraries were added. Developers should have some freedom to add new dependencies but they have to align with the guidelines of the project and should be well maintained. Ideally they should also be known to the architect and documented accordingly in the architecture documentation.
- **Testing:** Check if the amount of test makes sense. Discuss with the developers if there’s too many or too little tests.
- **Ask the developers:** Ask what is currently bad, where are the problems etc.? Usually experienced developers already know problematic code and can point out issues. Listen to them to learn what’s bothering them.
- **Try to simplify:** If you think a slice of code is too complicated or aren’t sure if it needs to be this complicated then check it out and try to simplify it - either you learn why it is this complicated or it really can be simplified.