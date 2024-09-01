# githubactions

An exercise to write a linter github action that will check for linting errors on the code that is pushed.

The event that triggers the workflow is "push". This can be changed to any trigger action.

"on: push"
	
	This specifies the event that triggers the workflow. This means the workflow will be executed every time code is pushed to the repository.

jobs: 

	This begins the definition of one or more jobs that the workflow will perform. A job is a set of steps that are executed sequentially on a runner (a container)

The runner is latest ubuntu image. This can be customised to any other image.

"runs-on: ubuntu-latest"

	Indicates the job should run on a container with the latest version of Ubuntu available at the time. GitHub provides and maintains these containers.


"uses: actions/checkout@v2"

	This action checks out the repository's code so that subsequent steps can operate on it. Essentially, it pulls the repository's code to the runner.


"uses: github/super-linter@v3.17.0"

	Specifies that the step should use the 'github/super-linter' action. This GH action runs a collection of linters to help validate your codebase for adherence to coding standards.

"env"

	This defines environment variables that will be passed to the Super-Linter action. These variables control it's behavior.

	"DEFAULT_BRANCH: master"

	Sets DEFAULT_BRANCH env variable to master. Super-linter uses this to identify the default branch of the repository.

	"GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}"

	Sets GITHUB_TOKEN environment variable, using a special secret provided by GH. It is a built-in secret that GH automatically creates for each workflow run. Used to authenticate the workflow so it can interact with the repository, such as making API requests to Github.




