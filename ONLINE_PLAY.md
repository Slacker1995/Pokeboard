# Playing PokéBoard online

Choose **ONLINE** on the main menu. One computer hosts the adventure, and each other trainer joins from their own computer. Rooms support two to six trainers.

## Start an adventure

1. The host enters their name, chooses a partner and clicks **HOST GAME**. Leave the port at **28961** unless you need a different one.
2. The room displays the host's local addresses and port. Share the appropriate address with the other players.
3. Other players enter their names, choose different partners, enter the host's address and matching port, then click **JOIN GAME**.
4. The host chooses Quick, Standard or Full Kanto. Everyone clicks **READY**, then the host clicks **START ADVENTURE**.

Each partner is available to one trainer. Changing the adventure length clears readiness so everyone can review the choice.

Everyone watches the active trainer's adventure. Your controls work when your trainer needs to act. Rival battles pass control between the two participants, and trades ask the appropriate trainer to choose and confirm. The host runs the game, including its map, custom Pokémon, sprites, encounters and rules. Guests do not need matching editor profiles.

## Connect from another home

On the same home network, use the host address displayed in the room, such as `192.168.1.25`. For players elsewhere, the host needs a reachable public address and may need to forward the chosen **UDP** port to their computer and allow the game through their firewall. Use the same port on every computer. The game does not change router or firewall settings for you. Some connections require a private network service or an internet connection that permits incoming traffic. Godot's [multiplayer networking guide](https://docs.godotengine.org/en/4.7/tutorials/networking/high_level_multiplayer.html) explains direct connections and port forwarding.

The first version uses a shared game picture and audio, so picture updates and input response depend on the host's upload speed and everyone's connection. The host must keep the game running. This is direct hosting; there is no room-code or matchmaking service.

## Save and continue later

The host has a **SAVE** button in the online panel. Save while on the main board between actions, then choose a slot. Players wait while the host uses the save screen. Encounters, battles and Safari visits must finish before saving.

To continue later:

1. The original host opens **ONLINE → HOST GAME → CONTINUE SAVE** and loads the adventure.
2. Other players join in the original trainer order. The saved trainer names and partners appear automatically; the host controls the first saved trainer.
3. The room requires the same number of trainers as the save. Everyone readies up, and the host starts the adventure.

The saved Pokémon, items, badges, cards, map, events and board turn resume together. A one-trainer local adventure cannot become an online room. Load a save in the lobby; an adventure already in progress cannot be replaced from the online game menu.

## Reconnect and sound options

If a trainer disconnects, further game input pauses and their place stays reserved. Click **RECONNECT** to return. The guest remembers the last successful connection privately on that computer, so reopening the game and selecting **ONLINE → RECONNECT** can reclaim the trainer while the host's room is still running. A new guest cannot join an adventure already in progress.

Each computer's online **OPTIONS** button has Master, Music and Sound Effects sliders. These affect sound on that computer. The **LEAVE** button asks for confirmation; leaving as host closes the room for everyone.

This player edition has no editor, debug or test-battle tools. The bundled map and rules are ready for play. Online guests control their own gameplay and can always use their local sound options or leave the room.
