# 📦 {{cookiecutter.package_name}}

{{cookiecutter.description}}

---

## ⬇️ Installation

### 🔑 Get personal access token

> Get personal access token from [GitLab](https://{{cookiecutter.gitlab_host}}/-/profile/personal_access_tokens)

```bash
export GL_USERNAME=<your_gitlab_username> # <- your gitlab username
export GL_TOKEN=<your_personal_access_token> # <- your personal access token
```

where:

- `GL_USERNAME` - your gitlab username (for example ilya)
- `GL_TOKEN` - your personal access token with access to python-package-index
  repository (for example 5WJpU5v_ms53z6xDt_nG)

> full example:
>
> ```bash
> export GL_USERNAME=ilya
> export GL_TOKEN=5WJpU5v_ms53z6xDt_nG
> ```

### 💾 Add gitlab credentials to .netrc

```bash
echo "
machine gitlab.amazmetest.ru login $GL_USERNAME password $GL_TOKEN
" >> ~/.netrc
```

### 🦫 Go module

```bash
go get {{cookiecutter.go_module_name}}
```

## 🎂 Usage

```golang
package main

import (
	"fmt"
	"rock-paper-scissors/utils"

	"github.com/fatih/color"
)

func main() {
	var totalScore = map[string]int{"Computer": 0, "User": 0, "Tie": 0, "Rounds": 0}
	var playAgain bool = true

	for playAgain {
		userChoice := utils.GetUserChoice()
		computerChoice := utils.GenerateComputerChoice()

		fmt.Println("User choice: ", userChoice)
		fmt.Println("Computer choice: ", computerChoice)

		winner := utils.CalculateWinner(computerChoice, userChoice)
		totalScore[winner]++
		totalScore["Rounds"]++

		playAgain = utils.PlayAgain()
	}

	fmt.Println("Thanks for playing, here's the final results")
	fmt.Println("--------------------------------------------")
	fmt.Printf("User: %v\n", totalScore["User"])
	fmt.Printf("Computer: %v\n", totalScore["Computer"])
	fmt.Printf("Tie: %v\n", totalScore["Tie"])
	fmt.Printf("Number of games played: %v\n", totalScore["Rounds"])

	if totalScore["User"] > totalScore["Computer"] {
		color.Green("Final result: Congratualations, you won overall!")
	}

	if totalScore["User"] < totalScore["Computer"] {
		color.Red("Final result: The computer did better overall. Better luck next time.")
	}

	if totalScore["User"] == totalScore["Computer"] {
		color.Yellow("Final result: It was a tie overall.")
	}
}
```

## 🎩 Contributing

Read our [guide](CONTRIBUTING.md) to contribute.
