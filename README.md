**JJK Combat System**
The system is complete, but I couldn't get animations and VFX for it. But everything is well arranged, and the system is scalable 


A server-authoritative Roblox combat system based on *Jujutsu Kaisen*.  
It focuses on modular architecture, responsive combat mechanics,  
and fully data-driven character design.

All combat actions are validated on the **server**, preventing common  
exploits and ensuring consistent gameplay across all players.

Currently, four characters are implemented:

- **Gojo**
- **Sukuna**
- **Megumi**
- **Yuji**

Each character has unique cursed energy limits, passive abilities,  
and combat techniques.

Abilities are mapped to the keys **Q, E, R, and F**, with **F** reserved  
for powerful **Domain Expansions** that temporarily alter the battlefield  
and deal continuous damage to nearby players.

Combat follows a structured sequence.  
When a player attempts to use a move, the client sends a request to  
the server. The server then validates cooldowns, stun states, cursed  
energy availability, and player status before executing the attack.

If the move is valid, cursed energy is consumed, hit detection runs,  
damage is applied, and the results are synchronized back to all clients.

Key mechanics include:

- Cursed Energy management  
- Passive character abilities  
- Combo attacks  
- Rare events such as **Black Flash**

The system is fully **data-driven**, allowing new characters and  
abilities to be added through configuration tables without modifying  
the core combat logic.

ServerScriptService/
├── Combat/
│   ├── CombatService
│   ├── CursedEnergyService
│   ├── CharacterService
│   ├── PassiveService
│   ├── AbilityService
│   └── DomainService
│
├── Handlers/
│   └── ShopRemoteHandler
│
└── Services/
    ├── ShopService
    ├── InventoryService
    ├── CurrencyService
    ├── DataService
    ├── StateService
    └── DataStoreService

ReplicatedStorage/
└── Shared/
    ├── CharacterConfig
    └── ItemConfig

StarterPlayerScripts/
├── AbilityController
└── CombatUI
