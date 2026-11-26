# TU Delft's ibex-Games organization

This repo makes the games listed in games.yaml findable for the IBEX-infrastructure.
Through this repo, the IBEX team shares the games and components we build for simulations and experiments so they can be 
inspected, adapted and reused. 
With this repository, our 

- `organization.yaml` gives the organization's name within the admin panel of the ibex server (`tudelft`:
  its games are `tudelft.<game>`) and for people ("TU Delft").
- `games.yaml` lists its games, each by the name of its repository in the
  same GitHub organization (every game of the organization is one).

An installation of the IBEX-server that knows this github-organization lists its games
on the discovery page (Discover games). When you select a game in the discovery page,
the server downloads its repository, on its default branch, into the workspace of the server,
`games/tudelft/<game>`. After this download, it automatically installs it, certifies it and sets it up with its AI
agents. 

The installer for the IBEX libraries (https://github.com/IBEX-TUDelft/ibex-starting-point) 
adds TU Delft to every new workspace, and running :
`npx ibex organization add https://github.com/IBEX-Games` 
within your working folder adds it to any other.

Add only organizations you trust: downloading a game runs its code.

| Game | Full name | Repository | AI agents |
|---|---|---|---|
| Prisoner's Dilemma | `tudelft.prisoner_dilemma` | [IBEX-TUDelft/prisoner_dilemma](https://github.com/IBEX-Games/prisoner_dilemma) | yes |

## Adding a game

Its repository goes into the GitHub organization `IBEX-Games`; then add a
line to `games.yaml`: the game's name (its `game.yaml`'s `id`; listed here,
it is the game `tudelft.<id>`: a game never names its organization) and its
repository's name:

```yaml
prisoner_dilemma: prisoner_dilemma
my_game: my_game
```

The organization says nothing about versions: a game is downloaded from its
default branch, and says itself which ibex and econagents it works with (its
`game.yaml`'s `setup`). Keep a game's default branch certified (`npm run
certify`).
