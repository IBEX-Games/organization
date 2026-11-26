# TU Delft's ibex-Games organization

The repository named `organization` of the GitHub organization
`IBEX-Games`: it makes `IBEX-Games` the ibex organization for 
the simulation and experiments server of TU Delft.

- `organization.yaml` gives the organization's name for ibex (`tudelft`:
  its games are `tudelft.<game>`) and for people ("TU Delft").
- `games.yaml` lists its games, each by the name of its repository in the
  same GitHub organization (every game of the organization is one).

A workspace that knows the organization (its `organizations.yaml`; the
installer adds TU Delft to every new workspace, and `npx ibex organization
add https://github.com/IBEX-Games` adds it to any other) lists its games
on the discovery page (Discover games), and downloads one by cloning its
repository, on its default branch, into the workspace's
`games/tudelft/<game>`, installing it, certifying it and setting up its AI
agents. Add only organizations you trust: downloading a game runs its code.

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
