---
title: "Soundhound"
type: page
---

![Soundhound logo](https://media.licdn.com/dms/image/v2/D4E0BAQFKcywWq3s33A/company-logo_200_200/B4EZdBNX3vHcAQ-/0/1749145714928/soundhoundai_logo?e=1756339200&v=beta&t=UEb7uEoqaFE_MD7xCx6GU5zCS4yLob-TmqppTgwxi48)

# Software engineer - Deep learning

I worked as a Software Engineer in the speech recognition team.

My main project was to work on a repository performing training of neural networks for speech recognition. This repository is used by many developers at SoundHound in order to train speech recognition models for different languages.

The existing code was already performing the training on a single GPU with pytorch. To speed it up, I adapted the code so that it can run on multiple GPUs. To do this, I needed to adapt different sections of the code (data loading, batching, computation of validation metrics..). I also needed to make sure that the final trained model had similar performance than one trained on a single GPU.

I also tried to democratize coding good practices in my team by:
- refactoring, documenting and testing sections of the code
- encouraging the use of type hinting and modern Python libraries such as Pydantic (for data validation), Typer (for CLIs), pathlib...
- implementing an internal repository that showcases different tools for python repositories:
  - configuration of a CI with docker building, unit testing and coverage computation, linting with pylint and mypy...
  - configuration of pre-commit hooks (black, isort, autoflake...) to ensure a consistent coding style
