CATEGORY: General and Core Signatures
----------------------------------------
NAME: ActionEffect
SIG:  40 55 56 57 41 54 41 55 41 56 41 57 48 8D AC 24
DESC: What it is: A general action effect handler used when the game applies the results of an action to a target. When it runs: After an action has been resolved and the client is processing damage, healing, status changes, or similar results. Why you would care: Use this if you want to react to actions actually landing instead of just being requested.
----------------------------------------
NAME: ActorVfx_Create
SIG:  40 53 55 56 57 48 81 EC ?? ?? ?? ?? 0F 29 B4 24 ?? ?? ?? ?? 48 8B 05 ?? ?? ?? ?? 48 33 C4 48 89 84 24 ?? ?? ?? ?? 0F B6 AC 24 ?? ?? ?? ?? 0F 28 F3 49 8B F8
DESC: What it is: The function that creates a visual effect attached to a character or other game object. When it runs: When the client starts a new attached effect such as a skill effect, aura, or visual indicator. Why you would care: Use this if you want to watch actor-attached effects being created or identify which effects are starting.
----------------------------------------
NAME: ActorVfx_Destructor
SIG:  48 89 5C 24 ?? 57 48 83 EC ?? 48 8D 05 ?? ?? ?? ?? 48 8B D9 48 89 01 8B FA 48 8D 05 ?? ?? ?? ?? 48 89 81 ?? ?? ?? ?? 48 8B 89 ?? ?? ?? ?? 48 85 C9 74 ?? 48 8B 01 48 8B D3
DESC: What it is: The cleanup function for a visual effect attached to a game object. When it runs: When the client removes an attached effect and releases its internal resources. Why you would care: Use this if you want to know when an attached effect ends or is being torn down.
----------------------------------------
NAME: AtkUnitBase_ReceiveEvent
SIG:  48 89 5C 24 ?? 48 89 74 24 ?? 57 48 83 EC 30 0F B7 FA
DESC: What it is: The main input handler for game UI windows built on AtkUnitBase. When it runs: When the player clicks, presses keys, changes focus, or otherwise interacts with a supported UI window. Why you would care: Use this if you want a broad hook for UI interaction without targeting one specific addon first.
----------------------------------------
NAME: AutoMoveController
SIG:  48 8D 0D ?? ?? ?? ?? E8 ?? ?? ?? ?? 48 8D 0D ?? ?? ?? ?? E8 ?? ?? ?? ?? 84 C0 74 23
DESC: What it is: A pointer to the game's automatic movement controller, which handles autorun-style movement. When it runs: You read this when you need the controller; the controller itself is active whenever automatic movement is in use. Why you would care: Use this if you want to inspect or control automatic movement state.
----------------------------------------
NAME: BaseClassJobIDs
SIG:  01 00 00 00 02 00 00 00 03 00 00 00 ...
DESC: What it is: A static list of the base class row ids used by the game. When it runs: This is data, so you read it when you need the built-in class list. Why you would care: Use this if you want a quick in-client reference for base classes without hardcoding your own table.
----------------------------------------
NAME: Blacklist_DataPointer
SIG:  89 50 4E 48 48 A5 41 0E 4C
DESC: What it is: A pointer used to reach the client's blacklist-related data. When it runs: You read this when you need the current blacklist storage. Why you would care: Use this if you want to inspect, mirror, or extend blacklist-related behavior.
----------------------------------------
NAME: CutsceneHandleInput
SIG:  48 89 5C 24 ?? 48 89 6C 24 ?? 48 89 74 24 ?? 57 48 83 EC 40 48 8B 05 ?? ?? ?? ?? 48 33 C4 48 89 44 24 ?? 80 79 28 00
DESC: What it is: The function that handles input while a cutscene is active. When it runs: While the player is in a cutscene and the game is checking for skip or confirm input. Why you would care: Use this if you want to react to cutscene input or study how the client handles skipping.
----------------------------------------
NAME: Cutscene_SkipCondition
SIG:  75 11 BA ?? ?? ?? ?? 48 8B CF E8 ?? ?? ?? ?? 84 C0 74 4C
DESC: What it is: A small branch point tied to whether the client allows a cutscene to be skipped. When it runs: During the game's cutscene skip checks. Why you would care: Use this if you want to detect or patch the condition that controls skipping.
----------------------------------------
NAME: DirectorUpdate
SIG:  40 53 57 48 83 EC 58 48 8B 05 ?? ?? ?? ?? 48 33 C4 48 89 44 24 ?? 41 8B F9
DESC: What it is: A central update function for directors, the systems that manage duties, encounters, and other controlled game content. When it runs: Repeatedly while a director-controlled activity is active. Why you would care: Use this if you want a deep hook into duty or encounter state changes.
----------------------------------------
NAME: DynamicHousingSig_LotteryResult
SIG:  48 8B 70 FD ?? ?? 18 41 B5 ?? ?? 4C 20 50 68 0F ?? ?? E4
DESC: What it is: A pattern used to find the client's housing lottery result data. When it runs: You scan for it when you need the current lottery result structure in memory. Why you would care: Use this if you want to read or track housing lottery result information.
----------------------------------------
NAME: DynamicHousingSig_Placard
SIG:  33 78 C0 DA 8D ?? ?? ?? ?? 2F F2 18 BA 10 5B 0F CB 49 BA 40
DESC: What it is: A pattern used to locate the in-memory placard structure for a housing plot. When it runs: You scan for it when you need live placard data from the current plot context. Why you would care: Use this if you want to inspect placard details without relying on a UI scrape.
----------------------------------------
NAME: DynamicHousingSig_PlotData
SIG:  0F ?? ?? 4D D5 40 ?? ?? DD BA 41 ?? ?? ?? ?? CD ?? ?? 4D BA 89 08 70 4D ?? ?? BA 8D EB C4 58 ?? ?? ?? ?? 89 E5
DESC: What it is: A pattern used to find the client's housing plot data inside the larger game state. When it runs: You scan for it when you need direct access to plot-level housing information. Why you would care: Use this if you want raw housing plot data instead of reading it indirectly from UI or text.
----------------------------------------
NAME: DynamicHousingSig_WardInfo
SIG:  4C 8D FC 89 41 40 CA ED F0 CB ?? ?? E6 41 CD 12 F8
DESC: What it is: A pattern used to locate the ward information structure for housing areas. When it runs: You scan for it when you need the currently loaded ward data. Why you would care: Use this if you want to track ward-level housing details as the player moves between areas.
----------------------------------------
NAME: FlyText_PatchDisable
SIG:  E9 80 02 00 00 90
DESC: What it is: The replacement bytes that restore one fly-text patch point to its disabled state. When it runs: You write these bytes when turning that patch off. Why you would care: Use this if you are patching fly text and need the exact bytes to undo your change cleanly.
----------------------------------------
NAME: FlyText_PatchEnable
SIG:  0F 85 7F 02 00 00
DESC: What it is: The replacement bytes that enable the main fly-text patch. When it runs: You write these bytes when turning that patch on. Why you would care: Use this if you want to control the fly-text system through a direct patch.
----------------------------------------
NAME: FlyText_PatchSig
SIG:  83 3D ?? ?? ?? ?? ?? 0F 85 ?? ?? ?? ?? F3 0F 10 0F
DESC: What it is: The scan pattern for the main fly-text patch location. When it runs: You scan for it before writing either the enabled or disabled patch bytes. Why you would care: Use this if you need a stable way to find the fly-text patch point after updates.
----------------------------------------
NAME: FlyText_SubPatchDisable
SIG:  75 58 F3 0F 10 0F
DESC: What it is: The replacement bytes that restore the secondary fly-text patch point to its disabled state. When it runs: You write these bytes when turning the secondary patch off. Why you would care: Use this if your fly-text patching logic uses a second branch or helper patch point.
----------------------------------------
NAME: FlyText_SubPatchEnable
SIG:  EB 58 F3 0F 10 0F
DESC: What it is: The replacement bytes that enable the secondary fly-text patch. When it runs: You write these bytes when turning the secondary patch on. Why you would care: Use this if you need both patch points for complete fly-text behavior changes.
----------------------------------------
NAME: FlyText_SubPatchSig
SIG:  83 3D ?? ?? ?? ?? ?? 75 58
DESC: What it is: The scan pattern for the secondary fly-text patch location. When it runs: You scan for it before applying or reverting the secondary fly-text patch. Why you would care: Use this if one fly-text patch point is not enough for the behavior you want.
----------------------------------------
NAME: GameObject_ctor
SIG:  48 8D 05 ?? ?? ?? ?? C7 81 ?? ?? ?? ?? ?? ?? ?? ?? 48 89 01 48 8B C1 C3
DESC: What it is: The base constructor for core game objects such as players, NPCs, and world objects. When it runs: When the client is building a new game object instance. Why you would care: Use this if you need a low-level hook at object creation time.
----------------------------------------
NAME: GameVersion_DataPointer
SIG:  E8 ?? ?? E0 0F F1 ?? ?? EB 4C DA 05 8B ?? ?? ?? ?? C2 CF
DESC: What it is: A pointer used to read the current game version data. When it runs: You read it when your plugin needs to verify client version compatibility. Why you would care: Use this if you need to guard offsets, signatures, or data layouts by version.
----------------------------------------
NAME: GetNameplateColor
SIG:  48 89 5C 24 ?? 48 89 6C 24 ?? 48 89 74 24 ?? 57 48 83 EC 20 48 8B 35 ?? ?? ?? ?? 48 8B F9
DESC: What it is: The function that decides the color used for a target or nameplate. When it runs: When the game needs to draw or refresh nameplate colors. Why you would care: Use this if you want to inspect or change how nameplate colors are chosen.
----------------------------------------
NAME: GrandCompanyRankIDs
SIG:  00 00 00 00 01 00 00 00 02 00 00 00 ...
DESC: What it is: A static list of row ids for Grand Company ranks. When it runs: This is data, so you read it when you need the built-in rank list. Why you would care: Use this if you want the in-client rank set without maintaining your own table.
----------------------------------------
NAME: HousingDataPointer_YGirK
SIG:  48 8B CD 49 18 38 D2 E4 D0 ?? ?? ?? ?? 8B 41 95 49 D1
DESC: What it is: A primary pointer into the housing manager data used for plot status and lottery details. When it runs: You read it when you need current housing manager state. Why you would care: Use this if you want direct access to plot availability or lottery-related data.
----------------------------------------
NAME: HousingDataPointer_xefoT
SIG:  48 89 5C 24 8D F1 50 ?? ?? ?? ?? 30 ?? ?? F8 ?? ?? ?? ?? 9F CD 58 C0 28 68 41 33 CB
DESC: What it is: A secondary pointer into housing data, used for related ward or placard details. When it runs: You read it when the primary housing pointer is not enough for the information you need. Why you would care: Use this if you are mapping multiple housing structures and need the neighboring state.
----------------------------------------
NAME: HousingItemCategories_Special
SIG:  64 00 00 00 27 00 00 00 70 00 00 00
DESC: What it is: A static list of item category ids for special housing-related items. When it runs: This is data, so you read it when filtering or grouping housing items. Why you would care: Use this if you need a ready-made list of housing-specific item categories.
----------------------------------------
NAME: HousingPriceDepreciationConstants
SIG:  EA 07 00 00 02 00 00 00 01 00 00 00
DESC: What it is: A small constant table used in housing price depreciation logic. When it runs: This is data, so you read it when reproducing or checking plot price calculations. Why you would care: Use this if you want your housing price math to match the client.
----------------------------------------
NAME: HousingPriceIndex_Lookup
SIG:  00 2D 31 01 04 5C 36 00 70 38 39 00 ...
DESC: What it is: A lookup table that maps housing plot indices to pricing information. When it runs: This is data, so you read it during housing price lookups. Why you would care: Use this if you want to resolve plot ids into the matching price table entry.
----------------------------------------
NAME: HousingPriceScale_Ward
SIG:  80 A8 12 01 C0 C6 2D 00 E0 CA D4 02 ...
DESC: What it is: A static table of housing price scale values by ward or related grouping. When it runs: This is data, so you read it when calculating or comparing ward-adjusted prices. Why you would care: Use this if you want more accurate housing price calculations.
----------------------------------------
NAME: HousingPriceTable_Large
SIG:  C0 EA 21 01 E0 CA D4 02 2C A3 30 00 ...
DESC: What it is: The built-in base price table for large housing plots. When it runs: This is data, so you read it when calculating or displaying large plot prices. Why you would care: Use this if you want your plugin to use the same base prices as the client.
----------------------------------------
NAME: HousingPriceTable_Medium
SIG:  70 38 39 00 C0 EA 21 01 C0 C6 2D 00 ...
DESC: What it is: The built-in base price table for medium housing plots. When it runs: This is data, so you read it when calculating or displaying medium plot prices. Why you would care: Use this if you want client-matching medium plot prices.
----------------------------------------
NAME: HousingPriceTable_Small
SIG:  70 38 39 00 2C A3 30 00 98 7F 33 00 ...
DESC: What it is: The built-in base price table for small housing plots. When it runs: This is data, so you read it when calculating or displaying small plot prices. Why you would care: Use this if you want client-matching small plot prices.
----------------------------------------
NAME: InternalData_PjBOC
SIG:  E5 17 01 00 00 00 00 00 E5 17 01 00 00 00 00 00 E5 17 01 00 00 00 00 00 E5 17 01 00 00 00 00 00 E5 17 01 00 00 00 00 00 AE 00 01 00 00 00 00 00 AD 00 01 00 00 00 00 00 AE 00 01 00 00 00 00 00 AD 00 01 00 00 00 00 00 AE 00 01 00 00 00 00 00
DESC: What it is: A hardcoded byte array used by one internal feature in the client. When it runs: This is data, so you read it only when that specific feature is being studied or reproduced. Why you would care: Use this as a raw reference table if you have confirmed it belongs to the system you are reverse engineering.
----------------------------------------
NAME: InternalState_GlobalPointer
SIG:  48 83 EC ?? ?? F3 45 ED ?? ?? 87 ?? ?? ?? ?? ?? ?? 78 ?? ?? 49 ?? ?? ?? ?? F4 C0 49 E3 ?? ?? ?? ?? 83 68 4D 93 28 E8 40 F9
DESC: What it is: A pointer to a broader internal state structure used by one or more plugin-facing systems. When it runs: You read it when you need the current state block rather than a single field or function. Why you would care: Use this if you are mapping a whole feature and need its shared state object.
----------------------------------------
NAME: Inventory_SortHandler
SIG:  48 89 6C 24 ?? 48 89 74 24 ?? 57 48 83 EC 30 83 B9 ?? ?? ?? ?? ?? 41 8B F0
DESC: What it is: A function involved in inventory sorting. When it runs: When the game starts or processes an inventory sort operation. Why you would care: Use this if you want to watch, block, or react to sort requests.
----------------------------------------
NAME: ItemUICategoryIDs_Consumable
SIG:  08 00 00 00 28 00 00 00 0A 00 00 00 ...
DESC: What it is: A static list of item UI category ids for consumables. When it runs: This is data, so you read it when filtering or grouping consumable items. Why you would care: Use this if you want category-aware item filtering without your own hardcoded list.
----------------------------------------
NAME: ItemUICategoryIDs_Crafting
SIG:  10 00 00 00 11 00 00 00 08 00 00 00 ...
DESC: What it is: A static list of item UI category ids tied to crafting and gathering. When it runs: This is data, so you read it when grouping item categories for those systems. Why you would care: Use this if you want a client-based category list for crafting or gathering items.
----------------------------------------
NAME: ItemUICategoryIDs_Currency
SIG:  2C 00 00 00 2E 00 00 00 21 00 00 00
DESC: What it is: A static list of item UI category ids used for currencies and token-like items. When it runs: This is data, so you read it when filtering currency items. Why you would care: Use this if you want currency grouping that matches the client.
----------------------------------------
NAME: ItemUICategoryIDs_Gear
SIG:  0E 00 0F 00 0A 00 1E 00 0B 00 20 00 ...
DESC: What it is: A static list of item UI category ids for wearable gear and weapons. When it runs: This is data, so you read it when filtering or grouping equipment. Why you would care: Use this if you want your gear filters to align with the client's own category groupings.
----------------------------------------
NAME: ItemUICategoryIDs_Medicine
SIG:  08 00 00 00 28 00 00 00 0A 00 00 00
DESC: What it is: A static list of item UI category ids used for medicine-style items. When it runs: This is data, so you read it when filtering healing or status-clearing items. Why you would care: Use this if you need a medicine-focused item category filter.
----------------------------------------
NAME: ItemUICategoryIDs_Misc
SIG:  08 00 00 00 0A 00 00 00 28 00 00 00 ...
DESC: What it is: A static list of item UI category ids for assorted special-use items. When it runs: This is data, so you read it when sorting or filtering side-system items. Why you would care: Use this if you want a quick way to identify non-standard item groups.
----------------------------------------
NAME: ItemUICategoryIDs_Other
SIG:  03 00 00 00 04 00 00 00 39 00 00 00 ...
DESC: What it is: A static fallback list for item UI categories that do not fit the main groups. When it runs: This is data, so you read it when you need broader category coverage. Why you would care: Use this if you want to catch categories that gear or consumable filters miss.
----------------------------------------
NAME: Lifestream_SupportSig
SIG:  48 8D 0D ?? ?? ?? ?? E8 ?? ?? ?? ?? 48 8B 8B ?? ?? ?? ?? 48 85 C9 74 11 48 8B 01
DESC: What it is: A hook or pointer tied to travel logic used by world visit or teleport support. When it runs: When the client is handling the relevant travel state. Why you would care: Use this if you need a stable anchor near the game's travel-related logic.
----------------------------------------
NAME: MapEffect
SIG:  48 89 5C 24 ?? 48 89 6C 24 ?? 48 89 74 24 ?? 57 48 83 EC 20 8B FA 41 0F B7 E8
DESC: What it is: A function that processes map-driven effects and related state changes. When it runs: When the game applies an effect caused by the map or environment. Why you would care: Use this if you want to watch map mechanics, environmental visuals, or related transitions.
----------------------------------------
NAME: MarketBoard_ConfirmPurchase
SIG:  0F B6 FC ?? ?? ?? ?? 4C EC 18 ?? ?? ?? ?? E8 EA EB 0F 50
DESC: What it is: A function used when the Market Board opens or confirms the purchase flow. When it runs: When the client moves into purchase confirmation for a listing. Why you would care: Use this if you want to detect or inspect purchase confirmation events.
----------------------------------------
NAME: MarketBoard_ItemRequest
SIG:  48 89 5C 24 ?? 48 89 6C 24 ?? 48 89 74 24 ?? 57 48 83 EC 30 48 8B 5C 24 ?? 41 8B F0
DESC: What it is: A function that requests item-related data for the Market Board. When it runs: When the client asks for listing or item information from the Market Board flow. Why you would care: Use this if you want to track Market Board queries rather than final purchases.
----------------------------------------
NAME: MarketBoard_PurchaseHandler
SIG: 48 89 5C 24 ?? 48 89 6C 24 ?? 48 89 74 24 ?? 41 56 48 83 EC 20 45 0F B6 F1
DESC: What it is: A function that handles Market Board purchase processing on the client side. When it runs: During the purchase flow after the client receives or handles the relevant data. Why you would care: Use this if you want a deeper hook into Market Board buying behavior.
----------------------------------------
NAME: MarketBoard_PurchaseState
SIG:  4C 8B 8B ?? ?? CF 40 E8 FA 4C B8
DESC: What it is: A pointer or signature used to reach the client's current Market Board purchase state. When it runs: You read it while a purchase is pending or being resolved. Why you would care: Use this if you want to know whether a purchase is still in progress.
----------------------------------------
NAME: MarketBoard_ResultPointer
SIG:  4D 48 D5 8B EF 83 B8 50 83 DB ?? ?? ?? ?? 70 E8 4C 8B FD 18 41 DE C2 83 ?? ?? ?? ?? C8 F2 48 D6 ?? ?? 8E 5B C2 E8
DESC: What it is: A pointer used to locate the client's Market Board search result storage. When it runs: You read it after the client has loaded Market Board result data. Why you would care: Use this if you want direct access to listing results and prices.
----------------------------------------
NAME: MarketBoard_ScoutListPointer
SIG:  48 89 5C 24 20 ?? ?? 70 BA B8 D3 ?? ?? ?? ?? D4 ?? ?? 83 CE
DESC: What it is: A pointer used to reach the Market Board's scouted world or price tracking data. When it runs: You read it when the client has loaded or updated that scout list. Why you would care: Use this if you want direct access to that Market Board support data.
----------------------------------------
NAME: PartyKick_SB
SIG:  48 83 EC 28 E8 ?? ?? ?? ?? 84 C0 74 09
DESC: What it is: A small internal function tied to the party kick flow. When it runs: Around the time the client checks or starts a party removal action. Why you would care: Use this as a starting anchor if you want to study or hook the party kick process.
----------------------------------------
NAME: ProcessChatBox
SIG:  48 89 5C 24 ?? 48 89 74 24 ?? 57 48 83 EC 20 48 8B F2 48 8B F9 45 84 C9
DESC: What it is: The main function used to process outgoing chat text and chat commands. When it runs: When the player sends a message or enters a command into chat. Why you would care: Use this if you want to watch, alter, or generate outgoing chat behavior.
----------------------------------------
NAME: ProcessMapEffectEx
SIG:  40 55 41 57 48 83 EC ?? 48 83 B9
DESC: What it is: A more detailed map effect handler used for map-driven effect processing. When it runs: When the client applies a more complex map effect or related update. Why you would care: Use this if the simpler map effect hook is not enough for the behavior you are tracking.
----------------------------------------
NAME: ProcessZonePacketUp
SIG:  48 89 5C 24 ?? 48 89 74 24 ?? 4C 89 64 24 ?? 55 41 56 41 57 48 8B EC 48 83 EC 70
DESC: What it is: A function involved in handling outgoing zone-change traffic or related zone transition work. When it runs: As the client is preparing or processing a move between areas. Why you would care: Use this if you want to study zone transitions or hook logic near them.
----------------------------------------
NAME: QuestManager
SIG:  48 8D 0D ?? ?? ?? ?? 0F B6 D8 E8 ?? ?? ?? ?? 44 0F B6 C0
DESC: What it is: A pointer to the client's main quest manager. When it runs: You read it when you need access to current quest state. Why you would care: Use this if you want a direct entry point into quest data.
----------------------------------------
NAME: Relogger_CharacterPointer
SIG:  83 08 49 ?? ?? ?? ?? 58 CA DF 48 ?? ?? ?? ?? 49 89 0F 0F 8D C0 83 50 40
DESC: What it is: A pointer used to reach character state involved in relogging logic. When it runs: You read it while tracking or automating relog-related behavior. Why you would care: Use this if you need stable access to the character context used during relogging.
----------------------------------------
NAME: SanitizeString
SIG:  48 89 5C 24 ?? 55 56 57 41 54 41 55 41 56 41 57 48 8D 6C 24 ?? 48 81 EC ?? ?? ?? ?? 48 8B 05 ?? ?? ?? ?? 48 33 C4 48 89 45 70 4D 8B F8 4C 89 44 24 ?? 4C 8B 05 ?? ?? ?? ?? 44 8B E2
DESC: What it is: A general string cleanup function used before text is displayed or processed. When it runs: When the client needs to sanitize text for chat or another UI-facing use. Why you would care: Use this if you want to inspect how the client cleans or normalizes text.
----------------------------------------
NAME: SendAction
SIG:  48 89 5C 24 ?? 48 89 6C 24 ?? 48 89 74 24 ?? 57 48 81 EC ?? ?? ?? ?? 48 8B 05 ?? ?? ?? ?? 48 33 C4 48 89 84 24 ?? ?? ?? ?? 48 8B E9 41 0F B7 D9
DESC: What it is: A low-level function that sends an action request from the client. When it runs: When the player uses an ability, item, or another action that needs to be sent out. Why you would care: Use this if you want a direct hook on action sending before the result comes back.
----------------------------------------
NAME: StaticVfx_Run
SIG:  E8 ?? ?? ?? ?? B0 02 EB 02
DESC: What it is: A function that updates a visual effect placed at a fixed world position. When it runs: While that static effect is active in the world. Why you would care: Use this if you want to watch or identify world-anchored effects instead of character-attached ones.
----------------------------------------
NAME: StaticVfx_ctor
SIG:  E8 ?? ?? ?? ?? F3 0F 10 35 ?? ?? ?? ?? 48 89 43 08
DESC: What it is: The constructor for a visual effect placed at a world location instead of on an actor. When it runs: When the client creates a static world effect. Why you would care: Use this if you want to catch the creation of fixed-position world effects.
----------------------------------------
NAME: StaticVfx_dtor
SIG:  40 53 48 83 EC 20 48 8B D9 48 8B 89 ?? ?? ?? ?? 48 85 C9 74 28 33 D2 E8 ?? ?? ?? ?? 48 8B 8B ?? ?? ?? ?? 48 85 C9
DESC: What it is: The cleanup function for a static world visual effect. When it runs: When the client removes that fixed-position effect. Why you would care: Use this if you want to know when a world effect has ended or been destroyed.
----------------------------------------
NAME: TargetingGuard_Hook
SIG:  40 53 48 83 EC 60 48 8B 05 ?? ?? ?? ?? 48 33 C4 48 89 44 24 ?? 48 85 D2
DESC: What it is: A low-level hook near the game's internal targeting logic. When it runs: When the client is updating or validating a target selection. Why you would care: Use this if you want to inspect, block, or alter targeting behavior at a deep level.
----------------------------------------
NAME: TargetingGuard_State
SIG:  B8 30 E1 CF C9 ?? ?? 38 FD ?? ?? 41 CD 00 4C 10 0F ED ?? ?? ?? ?? ?? ?? D3 40 8F E8 0F
DESC: What it is: A pattern used to locate the state block used by targeting-guard logic. When it runs: You read it when you need the current targeting-guard state. Why you would care: Use this if you want the shared state behind a targeting privacy or filtering feature.
----------------------------------------
NAME: WorldIDs_Chinese
SIG:  9C 04 00 00 9F 04 00 00 A2 04 00 00 ...
DESC: What it is: A static list of world ids for the Chinese region. When it runs: This is data, so you read it when you need that regional server list. Why you would care: Use this if you are building region-aware logic and want the in-client ids.
----------------------------------------
NAME: Blacklist_Proxy_BlockedCount
SIG:  Offset: 0x19F0
DESC: What it is: The offset to the number of blacklist entries inside the blacklist proxy structure. When it runs: You use it when reading that structure in memory. Why you would care: Use this if you want the current blacklist count without walking the full entry array first.
----------------------------------------
NAME: Blacklist_Proxy_EntryArray
SIG:  Offset: 0xF0
DESC: What it is: The offset to the start of the blacklist entry array inside the blacklist proxy structure. When it runs: You use it when reading blacklist entries from memory. Why you would care: Use this if you want to iterate the blacklist directly.
----------------------------------------
NAME: Blacklist_Proxy_EntrySize
SIG:  Size: 0x20
DESC: What it is: The size of each blacklist entry in the blacklist proxy array. When it runs: You use it while stepping through the array in memory. Why you would care: Use this if you want to calculate entry addresses correctly.
----------------------------------------
NAME: Blacklist_Proxy_IdentifierOffset
SIG:  Offset: 0x10
DESC: What it is: The offset to the account or content id field inside one blacklist entry. When it runs: You use it when reading an individual blacklist entry. Why you would care: Use this if you want the stable identifier instead of only the displayed name.
----------------------------------------
NAME: Blacklist_Proxy_NamePointerOffset
SIG:  Offset: 0x00
DESC: What it is: The offset to the player name pointer inside one blacklist entry. When it runs: You use it when reading an individual blacklist entry. Why you would care: Use this if you want the displayed name for each blacklist record.
----------------------------------------
NAME: ProcessChatBox
SIG:  48 89 5C 24 ?? 48 89 74 24 ?? 57 48 83 EC 20 48 8B F2 48 8B F9 45 84 C9
DESC: What it is: The same outgoing chat processor, noted here as a useful hook for issuing chat-driven blacklist commands. When it runs: When the player sends chat text or a chat command. Why you would care: Use this if your feature works by sending slash commands through the normal chat path.
----------------------------------------
NAME: UseAction_Hook
SIG:  FFXIVClientStructs: ActionManager.UseAction(40 53 55 56 41 54 41 55 41 56 41 57 48 81 EC 48 02 00 00 48 8B 05 ?? ?? ?? ?? 48 33 C4 48 89 84 24 D0)
DESC: What it is: A hook on ActionManager.UseAction, the function the client uses when sending an action request. When it runs: Right before the client attempts to use an action. Why you would care: Use this if you want to allow, block, log, or filter action usage based on your own rules.
----------------------------------------
CATEGORY: Limit Break
----------------------------------------
NAME: LimitBreakController_GetActionId
SIG:  48 89 5C 24 08 57 48 83 EC 20 41 0F B6 D8 48 8B F9 48 85 D2 74 33 80 FB 03 73 2E
DESC: What it is: The function that picks the correct Limit Break action id for an actor and LB tier. When it runs: When the client needs to validate or resolve which Limit Break action should be used. Why you would care: Use this if you want the exact action id behind the current Limit Break state.
----------------------------------------
NAME: LimitBreakController_InstanceRef
SIG:  48 8D 0D ?? ?? ?? ?? E8 ?? ?? ?? ?? 85 C0 75 0A B8 3E 02 00 00
DESC: What it is: A reference path to the global LimitBreakController object. When it runs: When the client checks Limit Break action state through the action system. Why you would care: Use this if you need the shared Limit Break controller rather than a single helper function.
----------------------------------------
NAME: LimitBreakController_IsValidLBActionForClass
SIG:  40 53 48 83 EC 20 41 8B D8 45 85 C0 74 34 48 8D 8A A0 01 00 00 E8 ?? ?? ?? ?? 8B C8 E8 ?? ?? ?? ??
DESC: What it is: A check that answers whether a given Limit Break action belongs to the actor's current job or role. When it runs: When the client is validating a Limit Break action before using or displaying it. Why you would care: Use this if you want to know whether an LB action id is valid for the current actor.
----------------------------------------
NAME: LimitBreakController_SetValues
SIG:  0F B6 44 24 28 88 41 0E 0F B6 44 24 30 88 41 0F 88 51 08 66 44 89 41 0A 66 44 89 49 0C C3
DESC: What it is: The function that writes the current Limit Break controller values into its fields. When it runs: When the client updates Limit Break availability, flags, or stored action ids. Why you would care: Use this if you want to watch the Limit Break state being refreshed in one place.
----------------------------------------
NAME: LimitBreakUI_Update
SIG:  40 57 48 83 EC 50 F6 81 A1 01 00 00 01 48 8B F9 44 0F 29 44 24 20 44 0F 28 C1 0F 84 ?? ?? ?? ??
DESC: What it is: The main update function for the Limit Break UI window. When it runs: While the Limit Break gauge is visible and the client is keeping the UI in sync. Why you would care: Use this if you want a UI-side hook for gauge changes, bar updates, or segment animation.
----------------------------------------
CATEGORY: Status Effects
----------------------------------------
NAME: StatusEffectListPlayerPacket
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B 1D ?? ?? ?? ?? 48 8B FA 48 85 DB 74 28
DESC: What it is: The packet handler that loads a player's status-effect list into the local status manager. When it runs: When the client receives the normal player status packet from the server. Why you would care: Use this if you want a direct hook when the client refreshes live status data from the network.
----------------------------------------
NAME: StatusManager_AddStatus
SIG:  66 85 D2 0F 84 ?? ?? ?? ?? 48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 48 83 EC 40
DESC: What it is: The function that adds or refreshes a status entry in an actor's status manager. When it runs: When the client applies a gained or updated status to an actor. Why you would care: Use this if you want to watch statuses being added or refreshed in real time.
----------------------------------------
NAME: StatusManager_EntryArray
SIG:  83 FA 3C 72 08 48 8D 05 ?? ?? ?? ?? C3 8B C2 48 C1 E0 04 48 83 C0 08 48 03 C1 C3
DESC: What it is: An accessor path that turns a status slot index into a pointer to the matching status entry. When it runs: When the client or plugin code looks up a specific status slot by index. Why you would care: Use this if you need the raw entry location instead of higher-level helper calls.
----------------------------------------
NAME: StatusManager_EntryCount
SIG:  45 33 D2 48 8D 41 10 45 8B CA 41 BB 00 00 00 E0 0F B7 48 F8 3B CA 75 0A 4D 3B C3 74 1B 4C 39 00 74 16 41 FF C2 49 FF C1 48 83 C0 10 49 83 F9 3C
DESC: What it is: A scan path that exposes the fixed slot count used by the status manager. When it runs: When the client loops through status slots looking for a match. Why you would care: Use this if you need the real status slot limit used by the client.
----------------------------------------
NAME: StatusManager_EntryParamOffset
SIG:  48 89 5C 24 08 48 89 7C 24 10 33 FF 4C 8D 49 10 44 8B DF 44 8B D7 BB 00 00 00 E0 0F 1F 44 00 00
DESC: What it is: An accessor path for the parameter field stored inside a status entry. When it runs: When the client looks up the extra value tied to a status, such as a stack-like or effect-specific number. Why you would care: Use this if you need more than just the status id and remaining time.
----------------------------------------
NAME: StatusManager_EntryRemainingTimeOffset
SIG:  83 FA 3C 72 04 0F 57 C0 C3 8B C2 48 03 C0 F3 0F 10 44 C1 0C
DESC: What it is: An accessor path for the remaining-time field inside a status entry. When it runs: When the client reads how much time is left on a status slot. Why you would care: Use this if you want remaining duration directly from the same data layout the client uses.
----------------------------------------
NAME: StatusManager_EntrySize
SIG:  83 FA 3C 72 08 48 8D 05 ?? ?? ?? ?? C3 8B C2 48 C1 E0 04 48 83 C0 08 48 03 C1 C3
DESC: What it is: The same index-to-entry accessor path, useful because it also reveals the size of each status entry. When it runs: When the client computes an entry address from a slot index. Why you would care: Use this if you need the exact entry stride for raw memory reads.
----------------------------------------
NAME: StatusManager_EntrySourceIdOffset
SIG:  83 FA 3C 72 03 33 C0 C3 8B C2 48 FF C0 48 03 C0 48 8B 0C C1 48 B8 ?? ?? ?? ?? ?? ?? ?? ?? 48 85
DESC: What it is: An accessor path for the source object id stored with a status entry. When it runs: When the client checks who applied a status. Why you would care: Use this if you need to know which actor caused a status effect.
----------------------------------------
NAME: StatusManager_EntryStatusIdOffset
SIG:  83 FA 3C 72 03 33 C0 C3 8B C2 48 03 C0 0F B7 44 C1 08 C3
DESC: What it is: An accessor path for the status id field inside a status entry. When it runs: When the client reads which status occupies a slot. Why you would care: Use this if you want the raw status id directly from the stored entry.
----------------------------------------
NAME: StatusManager_GetRemainingTime
SIG:  83 FA 3C 72 04 0F 57 C0 C3 8B C2 48 03 C0 F3 0F 10 44 C1 0C
DESC: What it is: A helper that returns the remaining duration for a status slot. When it runs: When the client needs the remaining time for a given status index. Why you would care: Use this if you want a simple hook for duration reads instead of manual pointer math.
----------------------------------------
NAME: StatusManager_GetStatusId
SIG:  83 FA 3C 72 03 33 C0 C3 8B C2 48 03 C0 0F B7 44 C1 08 C3
DESC: What it is: A helper that returns the status id stored in a given status slot. When it runs: When the client wants the status id for a particular index. Why you would care: Use this if you want a compact status-id lookup hook.
----------------------------------------
NAME: StatusManager_HasStatus
SIG:  45 33 D2 48 8D 41 10 45 8B CA 41 BB 00 00 00 E0 0F B7 48 F8 3B CA 75 0A 4D 3B C3 74 1B 4C 39 00
DESC: What it is: A search function that checks whether an actor currently has a particular status. When it runs: When the client wants a yes-or-no answer for status presence, with an optional source filter. Why you would care: Use this if you want the same status lookup behavior the client already relies on.
----------------------------------------
NAME: StatusManager_SetFirstHalf
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 48 83 EC 40 40 32 F6 C6 81 D8 03 00 00 1E
DESC: What it is: The function that writes the first half of an incoming status list into the local status manager. When it runs: When the client receives a normal status list packet and updates the first group of entries. Why you would care: Use this if you want a direct hook when the client writes incoming status data.
----------------------------------------
CATEGORY: PvP Status and Buff UI
----------------------------------------
NAME: PvPTeamStatus_OnSetup
SIG:  48 89 5C 24 20 55 56 57 41 54 41 55 41 56 41 57 48 83 EC 70 48 8B 05 ?? ?? ?? ?? 48 33 C4 48 89 44 24 60
DESC: What it is: The setup function for the PvP team status window. When it runs: When the game first builds that UI window and binds its controls. Why you would care: Use this if you want a clean hook when the PvP status window is being created.
----------------------------------------
NAME: PvPTeamStatus_OnRequestedUpdate
SIG:  48 89 74 24 10 57 48 83 EC 20 48 8B F9 E8 ?? ?? ?? ?? 48 8B C8 E8 ?? ?? ?? ?? 48 8B CF 48 8B B0 C0 02 00 00
DESC: What it is: A refresh function for the PvP team status window. When it runs: When the game has new values and wants the window to redraw using the latest data. Why you would care: Use this if you want a UI-side hook for updated PvP team status information.
----------------------------------------
NAME: PvPTeamStatus_ReceiveEvent
SIG:  66 83 FA 19 0F 85 ?? ?? ?? ?? 48 89 5C 24 08 57 48 83 EC 30 49 8B D9 48 8B F9 41 83 F8 01 75 57
DESC: What it is: The input handler for the PvP team status window. When it runs: When the player clicks or confirms something in that window. Why you would care: Use this if you want to track or respond to direct interaction with the PvP status UI.
----------------------------------------
NAME: PvP_StatusEffectListPlayerPacket
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B 1D ?? ?? ?? ?? 48 8B FA 48 85 DB 74 28 48 8B 03 48 8B CB
DESC: What it is: The player status packet handler used in PvP and non-PvP cases alike. When it runs: When the client receives a player status-effect update packet from the server. Why you would care: Use this if you want to watch incoming status data before the UI reads it.
----------------------------------------
NAME: PvP_StatusEffectListPlayerDoublePacket
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B 1D ?? ?? ?? ?? 48 8B FA 48 85 DB 74 2F 48 8B 03 48 8B CB
DESC: What it is: The larger player status packet handler used when more status entries need to be written. When it runs: When the client receives the double-length status-effect update packet. Why you would care: Use this if you need complete coverage for large status lists.
----------------------------------------
NAME: PvP_StatusManager_SetFirstHalf
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 48 83 EC 40 40 32 F6 C6 81 D8 03 00 00 1E
DESC: What it is: The same first-half status writer used when incoming status packet data is copied into memory. When it runs: When the client is applying the first group of status entries. Why you would care: Use this if you want a focused hook on the actual write step instead of the packet handler around it.
----------------------------------------
NAME: PvP_StatusManager_SetSecondHalf
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 48 89 7C 24 20 41 56 48 83 EC 40 40 32 FF C6 81 D8 03 00 00 3C
DESC: What it is: The status writer used for the larger incoming status list format. When it runs: When the client applies both halves of a double-length status update. Why you would care: Use this if you want one hook that covers the larger status write path.
----------------------------------------
NAME: StatusManager_GetSourceId
SIG:  83 FA 3C 72 03 33 C0 C3 8B C2 48 FF C0 48 03 C0 48 8B 0C C1 48 B8 ?? ?? ?? ?? ?? ?? ?? ?? 48 85
DESC: What it is: A helper that returns the source actor for a status slot. When it runs: When the client asks who applied the status stored in a given entry. Why you would care: Use this if you need the source of a status without reading the full entry manually.
----------------------------------------
NAME: StatusManager_GetParamForStatus
SIG:  48 89 5C 24 08 48 89 7C 24 10 33 FF 4C 8D 49 10 44 8B DF 44 8B D7 BB 00 00 00 E0 0F 1F 44 00 00
DESC: What it is: A helper that returns the extra parameter value tied to a matching status. When it runs: When the client wants the effect-specific value stored with that status and source pair. Why you would care: Use this if you need the extra status value that many plugins miss by only reading ids and timers.
----------------------------------------
NAME: StatusManager_GetStatusByIndex
SIG:  83 FA 3C 72 08 48 8D 05 ?? ?? ?? ?? C3 8B C2 48 C1 E0 04 48 83 C0 08 48 03 C1 C3
DESC: What it is: A helper that returns the raw status entry pointer for a slot index. When it runs: When the client needs direct access to the entry instead of just one field. Why you would care: Use this if you want the whole status record for a slot.
----------------------------------------
NAME: StatusManager_GetStatusIndex
SIG:  45 33 D2 48 8D 41 10 45 8B CA 41 BB 00 00 00 E0 0F B7 48 F8 3B CA 75 0A 4D 3B C3 74 1B 4C 39 00 74 16 41 FF C2 49 FF C1 48 83 C0 10 49 83 F9 3C
DESC: What it is: A search helper that returns the slot index for a matching status. When it runs: When the client needs the position of a status entry rather than just a true or false answer. Why you would care: Use this if your logic needs to reuse the same slot index later.
----------------------------------------
NAME: StatusManager_SetSecondHalf
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 48 89 7C 24 20 41 56 48 83 EC 40 40 32 FF C6 81 D8 03 00 00 3C
DESC: What it is: The function that writes the full larger status list into the local status manager. When it runs: When the client receives a double-length status packet and applies all entries. Why you would care: Use this if you want one hook for the complete large-list write path.
----------------------------------------
NAME: BuffStatusUI_OnSetup
SIG:  48 89 5C 24 10 48 89 6C 24 18 48 89 74 24 20 57 41 54 41 55 41 56 41 57 48 81 EC 80 00 00 00
DESC: What it is: The setup function for the HUD buff and status display. When it runs: When the game first builds that HUD element. Why you would care: Use this if you want a clean hook when the buff display is being created.
----------------------------------------
NAME: BuffStatusUI_Update
SIG:  40 56 48 83 EC 30 48 8B F1 E8 ?? ?? ?? ?? F6 86 A1 01 00 00 01 0F 84 ?? ?? ?? ?? 8B 86 98 01 00 00
DESC: What it is: The main update function for the HUD buff and status display. When it runs: While that HUD element is visible and the client is refreshing its state. Why you would care: Use this if you want a UI-side hook for ongoing buff bar changes.
----------------------------------------
CATEGORY: PvP State Checks
----------------------------------------
NAME: PvP_IsInPvP
SIG:  48 89 5C 24 08 57 48 83 EC 20 8B 15 ?? ?? ?? ?? 48 8B F9 8B 1D ?? ?? ?? ?? 85 D2 0F 45 DA
DESC: What it is: A check that answers whether the current character is in a PvP state. When it runs: When the client needs a yes-or-no answer for PvP rules on the current character. Why you would care: Use this if you want a simple character-level PvP gate for your plugin logic.
----------------------------------------
NAME: PvP_IsInPvPArea
SIG:  48 8B 05 ?? ?? ?? ?? 48 85 C0 75 01 C3 0F B6 40 3B C0 E8 ?? 24 ?? C3
DESC: What it is: A check for whether the current zone or content area is marked as PvP. When it runs: When the client needs to know if the player is standing in a PvP-enabled area. Why you would care: Use this if your plugin should only react in PvP zones.
----------------------------------------
NAME: PvP_IsInPvPInstance
SIG:  40 53 48 83 EC 20 48 8B 1D ?? ?? ?? ?? 48 85 DB 74 1E 48 8D 0D ?? ?? ?? ?? E8 ?? ?? ?? ?? 84 C0
DESC: What it is: A check for whether the player is inside an active PvP instance. When it runs: When the client needs to distinguish real match content from a zone that merely supports PvP rules. Why you would care: Use this if your plugin should only run inside live PvP duties.
----------------------------------------
CATEGORY: PvP Profile and Rank Data
----------------------------------------
NAME: PvPProfile_ReadPacket
SIG:  48 89 5C 24 08 8B 82 48 01 00 00 4C 8B D2 89 41 04 4C 8B C9 0F B6 82 69 08 00 00 41 B8 03 00 00 00
DESC: What it is: The function that copies incoming PvP profile and rank data into the local PvP profile structure. When it runs: When the client receives updated PvP profile data from the server. Why you would care: Use this if you want a direct hook when PvP profile values change from network data.
----------------------------------------
NAME: PvPProfile_GetPvPRank
SIG:  0F B6 05 ?? ?? ?? ?? FE C8 3C 02 77 09 0F B6 C0 0F B6 44 08 10 C3
DESC: What it is: A helper that returns the current PvP rank from the stored profile state. When it runs: When the client wants the player's current PvP rank number. Why you would care: Use this if you want a simple hook or lookup for the current PvP rank.
----------------------------------------
NAME: PvPProfile_GetCurrentRankExp
SIG:  40 53 48 83 EC 20 0F B6 05 ?? ?? ?? ?? 48 8B D9 FE C8 3C 02 77 3D 48 89 7C 24 30
DESC: What it is: A helper that returns the experience already earned toward the current PvP rank. When it runs: When the client wants the current progress value for the active rank. Why you would care: Use this if you want to display or track PvP rank progress.
----------------------------------------
NAME: PvPProfile_GetCurrentRankNeededExp
SIG:  48 83 EC 28 0F B6 05 ?? ?? ?? ?? FE C8 3C 02 77 5D 48 89 5C 24 30 48 89 74 24 38
DESC: What it is: A helper that returns how much experience is required to reach the next PvP rank. When it runs: When the client wants the target progress value for the current rank. Why you would care: Use this if you want to calculate or display PvP rank completion.
----------------------------------------
NAME: PvPProfile_InstanceRef
SIG:  48 8D 0D ?? ?? ?? ?? E8 ?? ?? ?? ?? 85 C0 B9 7E 71 00 00 0F 45 C8
DESC: What it is: A reference path to the global PvP profile object. When it runs: When the client resolves the shared PvP profile state for rank and profile reads. Why you would care: Use this if you want the profile object itself instead of calling one helper at a time.
----------------------------------------
CATEGORY: PvP Map
----------------------------------------
NAME: PvPMap_OnSetup
SIG:  48 89 5C 24 10 48 89 6C 24 20 56 57 41 56 48 83 EC 50 0F 29 74 24 40 48 8B F9
DESC: What it is: The setup function for the PvP map window. When it runs: When the game first builds the PvP map UI and binds its controls. Why you would care: Use this if you want a clean hook when the PvP map is being created.
----------------------------------------
NAME: PvPMap_OnRequestedUpdate
SIG:  4C 8B DC 53 56 57 41 57 48 81 EC E8 00 00 00 48 8B 05 ?? ?? ?? ?? 48 33 C4 48 89 84 24 80 00 00 00
DESC: What it is: A refresh function for the PvP map window. When it runs: When the game has new PvP map data and wants the window to redraw. Why you would care: Use this if you want a UI-side hook for map refreshes instead of just startup.
----------------------------------------
NAME: PvPMap_Update
SIG:  40 53 48 83 EC 20 48 8B D9 E8 ?? ?? ?? ?? 48 8D 05 ?? ?? ?? ?? 48 89 03 33 C0 48 89 83 38 02 00 00
DESC: What it is: The active update function for the PvP map window. When it runs: While the PvP map is open and the client is keeping it current. Why you would care: Use this if you want a live hook for ongoing map-state changes.
----------------------------------------
NAME: PvPMap_GetWindowBounds
SIG:  40 53 48 83 EC 20 48 83 B9 40 14 00 00 00 48 8B DA 74 15 48 8B 89 C8 00 00 00
DESC: What it is: A helper that returns the current on-screen bounds of the PvP map window. When it runs: When the client needs the map window size or position for layout or hit testing. Why you would care: Use this if you need the real window rectangle for overlay or input work.
----------------------------------------
CATEGORY: PvP Screen Hotbar
----------------------------------------
NAME: PvPScreenHotbar_OnSetup
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 8B DA 49 8B F0 BA 01 00 00 00 48 8B F9
DESC: What it is: The setup function for the PvP screen hotbar window. When it runs: When the game first builds that hotbar UI. Why you would care: Use this if you want a clean hook when the PvP screen hotbar is created.
----------------------------------------
NAME: PvPScreenHotbar_Update
SIG:  40 53 48 83 EC 20 48 8B D9 E8 ?? ?? ?? ?? 80 BB 40 02 00 00 00 74 22 48 8B 8B 38 02 00 00
DESC: What it is: The main update function for the PvP screen hotbar. When it runs: While the hotbar is visible and the client is refreshing its state. Why you would care: Use this if you want a live hook for hotbar changes while a PvP match is running.
----------------------------------------
NAME: PvPScreenHotbar_ReceiveEvent
SIG:  83 FA 01 7C 20 53 48 83 EC 20 48 8B D9 49 8B C8 E8 ?? ?? ?? ?? 84 C0 74 07 C6 83 41 02 00 00 01
DESC: What it is: The input handler for the PvP screen hotbar. When it runs: When the player clicks or otherwise interacts with that hotbar. Why you would care: Use this if you want to track direct player interaction with the PvP hotbar UI.
----------------------------------------
CATEGORY: Frontline Match UI
----------------------------------------
NAME: PvPFrontlineGauge_OnSetup
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 48 89 7C 24 20 41 56 48 83 EC 20 48 8B E9
DESC: What it is: The setup function for the Frontline gauge window. When it runs: When the game first builds the Frontline gauge UI. Why you would care: Use this if you want a clean hook when the gauge window is created.
----------------------------------------
NAME: PvPFrontlineGauge_OnRefresh
SIG:  48 83 EC 28 F6 81 A1 01 00 00 01 74 08 45 33 C9 E8 2B 00 00 00 B0 01 48 83 C4 28 C3
DESC: What it is: A refresh function for the Frontline gauge display. When it runs: When the game has updated match values and wants the gauge to redraw. Why you would care: Use this if you want a UI-side hook for gauge value changes.
----------------------------------------
NAME: PvPFrontlineHeader_OnSetup
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 8B FA 49 8B D8 BA 04 00 00 00 48 8B F1
DESC: What it is: The setup function for the Frontline header window. When it runs: When the game first builds the Frontline header UI. Why you would care: Use this if you want a clean hook when the header is created.
----------------------------------------
NAME: PvPFrontlineHeader_OnRequestedUpdate
SIG:  48 89 6C 24 10 48 89 74 24 18 57 48 83 EC 30 48 8B B2 C0 03 00 00 48 8B E9 48 8B 46 28
DESC: What it is: A refresh function for the Frontline header. When it runs: When the game has new scoreboard or match-state data for the header. Why you would care: Use this if you want a UI-side hook for Frontline header updates.
----------------------------------------
NAME: PvPFrontlineInfo_OnSetup
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 48 8B D9 49 8B F8 49 8B C8 8B F2
DESC: What it is: The setup function for the Frontline info window. When it runs: When the game first builds that info panel. Why you would care: Use this if you want a clean hook when the Frontline info UI appears.
----------------------------------------
NAME: PvPFrontlineInfo_OnRefresh
SIG:  48 83 EC 28 F6 81 A1 01 00 00 01 74 08 45 33 C9 E8 1B 00 00 00 B0 01 48 83 C4 28 C3
DESC: What it is: A refresh function for the Frontline info window. When it runs: When the game has updated match data for that panel. Why you would care: Use this if you want a UI-side hook for Frontline info updates.
----------------------------------------
CATEGORY: PvP Character Window
----------------------------------------
NAME: PvPCharacter_OnSetup
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 48 89 7C 24 20 41 54 41 56 41 57 48 83 EC 30
DESC: What it is: The setup function for the PvP character window. When it runs: When the game first builds that character UI and its PvP-specific panels. Why you would care: Use this if you want a clean hook when the PvP character window is created.
----------------------------------------
NAME: PvPCharacter_OnRequestedUpdate
SIG:  40 55 56 57 48 83 EC 50 F6 81 A1 01 00 00 01 49 8B F0 48 8B FA 48 8B E9 0F 84 ?? ?? ?? ??
DESC: What it is: A refresh function for the PvP character window. When it runs: When the game has new PvP profile or character values and wants the window to redraw. Why you would care: Use this if you want a UI-side hook for PvP character updates.
----------------------------------------
NAME: PvPCharacter_ReceiveEvent
SIG:  40 55 53 56 57 41 56 48 8D 6C 24 D1 48 81 EC E0 00 00 00 48 8B 05 ?? ?? ?? ?? 48 33 C4
DESC: What it is: The input handler for the PvP character window. When it runs: When the player clicks, changes tabs, or otherwise interacts with that window. Why you would care: Use this if you want to track direct interaction with the PvP character UI.
----------------------------------------
CATEGORY: Duel Request
----------------------------------------
NAME: PvPDuelRequest_Show
SIG:  40 53 48 83 EC 20 48 8B D9 E8 ?? ?? ?? ?? 80 8B A1 01 00 00 40 48 83 C4 20 5B C3
DESC: What it is: The function that shows the PvP duel request window. When it runs: When the game decides to display an incoming duel request. Why you would care: Use this if you want a clean hook when a duel request appears.
----------------------------------------
NAME: PvPDuelRequest_OnSetup
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 40 49 8B F0 0F 29 74 24 30 F3 0F 10 35 ?? ?? ?? ??
DESC: What it is: The setup function for the PvP duel request window. When it runs: When the game first builds that UI. Why you would care: Use this if you want a hook during creation of the duel request window.
----------------------------------------
NAME: PvPDuelRequest_ReceiveEvent
SIG:  66 83 FA 19 75 2E 53 48 83 EC 20 49 8B D9 45 85 C0 74 0B 41 83 F8 01 75 0C 41 8B D0
DESC: What it is: The input handler for the PvP duel request window. When it runs: When the player accepts, declines, or interacts with the duel request UI. Why you would care: Use this if you want to react to player decisions on duel prompts.
----------------------------------------
CATEGORY: Spectator UI
----------------------------------------
NAME: PvPSpectatorList_OnSetup
SIG:  48 89 5C 24 10 48 89 6C 24 18 48 89 74 24 20 57 48 81 EC B0 00 00 00 48 8B 05 ?? ?? ?? ?? 48 33 C4
DESC: What it is: The setup function for the PvP spectator list window. When it runs: When the game first builds the spectator list UI. Why you would care: Use this if you want a clean hook when the spectator list appears.
----------------------------------------
NAME: PvPSpectatorList_OnRequestedUpdate
SIG:  40 56 48 83 EC 30 48 89 5C 24 40 48 8B F1 48 8B 0D ?? ?? ?? ?? 49 8B D8 48 89 7C 24 50
DESC: What it is: A refresh function for the spectator list window. When it runs: When the game has new spectator or camera data and wants the window to redraw. Why you would care: Use this if you want a UI-side hook for spectator list updates.
----------------------------------------
NAME: PvPSpectatorCameraList_OnSetup
SIG:  40 53 48 83 EC 20 48 8B D9 E8 62 04 00 00 BA 11 00 00 00 48 8B CB E8 ?? ?? ?? ?? 48 8B C8
DESC: What it is: The setup function for the spectator camera list window. When it runs: When the game first builds the camera selection UI for spectating. Why you would care: Use this if you want a clean hook when the spectator camera list is created.
----------------------------------------
NAME: PvPSpectatorCameraList_OnRequestedUpdate
SIG:  F6 81 A1 01 00 00 01 74 2D 48 8B 82 B0 03 00 00 48 8B 50 28 48 63 42 04 83 F8 07 77 19
DESC: What it is: A refresh function for the spectator camera list. When it runs: When the game has updated spectator camera state and wants the list to redraw. Why you would care: Use this if you want a UI-side hook for camera option changes while spectating.
----------------------------------------
CATEGORY: PvP Team UI
----------------------------------------
NAME: PvPTeam_OnSetup
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 41 56 41 57 48 83 EC 30 44 8B F2 49 8B E8
DESC: What it is: The setup function for the main PvP team window. When it runs: When the game first builds that team UI. Why you would care: Use this if you want a clean hook when the PvP team window is created.
----------------------------------------
NAME: PvPTeam_Update
SIG:  40 53 48 83 EC 30 0F 29 74 24 20 48 8B D9 0F 28 F1 E8 ?? ?? ?? ?? 48 8D 8B B0 02 00 00
DESC: What it is: The active update function for the main PvP team window. When it runs: While the team UI is open and the client is keeping it current. Why you would care: Use this if you want a live hook for changes inside the team window.
----------------------------------------
NAME: PvPTeam_ReceiveEvent
SIG:  66 83 FA 19 0F 85 ?? ?? ?? ?? 4C 8B DC 49 89 73 20 41 56 48 83 EC 60 49 89 6B 10
DESC: What it is: The input handler for the main PvP team window. When it runs: When the player clicks, confirms, or otherwise interacts with that UI. Why you would care: Use this if you want to track or react to direct team-window interaction.
----------------------------------------
NAME: PvPTeamActivity_OnSetup
SIG:  40 53 55 56 57 41 56 48 81 EC 80 00 00 00 48 8B 05 ?? ?? ?? ?? 48 33 C4 48 89 44 24 78
DESC: What it is: The setup function for the PvP team activity window. When it runs: When the game first builds that activity UI. Why you would care: Use this if you want a clean hook when the team activity panel is created.
----------------------------------------
NAME: PvPTeamMember_OnSetup
SIG:  40 53 55 56 57 41 56 48 81 EC 00 01 00 00 48 8B 05 ?? ?? ?? ?? 48 33 C4 48 89 84 24 F0 00 00 00
DESC: What it is: The setup function for the PvP team member detail window. When it runs: When the game first builds the member detail UI. Why you would care: Use this if you want a clean hook when the member detail panel is created.
----------------------------------------
NAME: PvPTeamResult_OnSetup
SIG:  40 53 55 56 57 41 56 48 81 EC 90 00 00 00 48 8B 05 ?? ?? ?? ?? 48 33 C4 48 89 84 24 88 00 00 00
DESC: What it is: The setup function for the PvP team result window. When it runs: When the game first builds the result UI after a team-related PvP flow. Why you would care: Use this if you want a clean hook when the result panel appears.
----------------------------------------
CATEGORY: Crystalline Conflict / MKS UI
----------------------------------------
NAME: PvPMKSBattleLog_Update
SIG:  40 53 48 83 EC 30 0F 29 74 24 20 48 8B D9 0F 28 F1 E8 1A 08 00 00 0F 28 CE 48 8B CB
DESC: What it is: The active update function for the Crystalline Conflict battle log window. When it runs: While that battle log is open and the client is refreshing its visible state. Why you would care: Use this if you want a live hook for changes in the battle log UI.
----------------------------------------
NAME: PvPMKSHeader_OnSetup
SIG:  40 53 48 83 EC 20 48 8B D9 49 8D 48 10 E8 ?? ?? ?? ?? BA 19 00 00 00 88 83 30 03 00 00
DESC: What it is: The setup function for the Crystalline Conflict header window. When it runs: When the game first builds that header UI. Why you would care: Use this if you want a clean hook when the match header appears.
----------------------------------------
NAME: PvPMKSIntroduction_OnSetup
SIG:  48 89 5C 24 10 48 89 74 24 20 57 48 83 EC 20 48 83 B9 38 02 00 00 00 49 8B F8 8B DA 48 8B F1
DESC: What it is: The setup function for the Crystalline Conflict introduction window. When it runs: When the game first builds the match introduction UI. Why you would care: Use this if you want a clean hook when the introduction panel appears.
----------------------------------------
NAME: PvPMKSRankRating_OnSetup
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 30 49 8B D8 48 8B F1 83 FA 10 0F 8C ?? ?? ?? ??
DESC: What it is: The setup function for the Crystalline Conflict rank rating window. When it runs: When the game first builds the rank rating UI. Why you would care: Use this if you want a clean hook when rank rating information is shown.
----------------------------------------
CATEGORY: PvP Agents and Modules
----------------------------------------
NAME: PvPAgentGauge_ReceiveEvent
SIG:  C7 02 02 00 00 00 48 8B C2 C6 42 08 00 C3
DESC: What it is: A small receive-event handler for the PvP gauge agent. When it runs: When that agent receives a simple event and writes its updated state. Why you would care: Use this if you want a lightweight hook close to the gauge agent's own state handling.
----------------------------------------
NAME: PvpSetModule_VtableRef
SIG:  48 8D 05 ?? ?? ?? ?? 48 89 03 0F 57 C0 33 C0 0F 11 43 48 0F 11 43 58 48 89 43 68
DESC: What it is: A constructor-side signature that identifies the PvP set module's vtable setup. When it runs: When the client is constructing that module. Why you would care: Use this if you need a stable anchor for the PvP set module even when a named function is not ideal.
----------------------------------------
NAME: InstanceContentPvpDirector_VtableRef
SIG:  48 8D 05 ?? ?? ?? ?? C6 83 A0 1F 00 00 00 48 89 03 33 D2 48 8D 05 ?? ?? ?? ?? B9 00 02 00 00 48 89 83 60 04 00 00
DESC: What it is: A constructor-side signature that identifies the main PvP content director's vtable setup. When it runs: When the client is constructing the PvP content director. Why you would care: Use this if you need a stable anchor for the shared PvP director object.
----------------------------------------
CATEGORY: PvP Core Systems
----------------------------------------
NAME: Frontline_IsInFrontlineArea
SIG:  80 3D 9D F9 EB 01 12 0F 94 C0 C3
DESC: What it is: A check that answers whether the current territory is a Frontline area. When it runs: When the client needs a yes-or-no answer for Frontline territory state. Why you would care: Use this if your plugin should only react in Frontline zones.
----------------------------------------
NAME: Frontline_GetDirector
SIG:  48 8B 81 58 01 00 00 48 85 C0 74 1B 48 8B 88 D8 02 00 00 BA 03 80 00 00 66 39 51 02 75 09
DESC: What it is: The helper that resolves the active Frontline director from the event framework. When it runs: When the client needs the Frontline-specific director object for live match state. Why you would care: Use this if you want direct access to Frontline match control data.
----------------------------------------
NAME: Hotbar_ResetPvPHotbarsForClass
SIG:  48 83 EC 28 41 8B D0 E8 44 16 00 00 B0 01 48 83 C4 28 C3
DESC: What it is: A helper that resets a job's PvP hotbar layout to the default setup. When it runs: When the client needs to rebuild a PvP hotbar from its default state. Why you would care: Use this if you want to detect or trigger a reset of PvP hotbar data.
----------------------------------------
NAME: Hotbar_ResetPvPHotbarsForClassInner
SIG:  40 55 57 48 83 EC 58 48 8B 0D 22 2F D0 01 8B EA E8 4B B2 5D FF 48 8B F8 48 85 C0 0F 84
DESC: What it is: The worker function used behind the PvP hotbar reset path. When it runs: While the client is rebuilding the actual slot data for a PvP hotbar reset. Why you would care: Use this if you want the deeper write path rather than the outer reset helper.
----------------------------------------
NAME: RaptureHotbar_GetPvPSavedHotbarIndexForClassJobId
SIG:  48 89 5C 24 08 57 48 83 EC 20 8B CA 41 0F B6 F8 8B DA E8 B9 C9 92 FF 84 C0 75 75
DESC: What it is: A helper that maps a class or job id to the saved PvP hotbar slot set used by the hotbar module. When it runs: When the client needs to find the correct saved PvP hotbar entry for a job. Why you would care: Use this if you want to read or modify the job-to-hotbar mapping.
----------------------------------------
NAME: RaptureHotbar_PvPStateUpdateTask
SIG:  48 89 5C 24 18 56 48 83 EC 20 48 83 3D 96 87 23 02 00 48 8B D9 48 89 6C 24 30
DESC: What it is: A background task that reacts to PvP state changes and updates hotbar-related data. When it runs: When the client's PvP state changes and the hotbar module needs to follow along. Why you would care: Use this if you want a broader hook for PvP hotbar state changes.
----------------------------------------
NAME: UIModule_GetPvpSetModule
SIG:  48 8D 81 D8 65 09 00 C3
DESC: What it is: A helper that returns the PvP set module from the main UI module. When it runs: When the client or plugin code needs the shared PvP set module pointer. Why you would care: Use this if you want an easy path to the module that stores PvP set data.
----------------------------------------
NAME: PvpSetModule_ReadFile
SIG:  84 D2 74 48 4D 85 C0 74 43 B8 90 01 00 00 66 44 3B C8 72 38 41 0F 10 40 10 0F 11 41 48
DESC: What it is: The function that reads saved PvP set data from disk into memory. When it runs: When the client loads persisted PvP configuration. Why you would care: Use this if you want a hook when stored PvP set data is loaded.
----------------------------------------
NAME: PvpSetModule_WriteFile
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B 01 48 8B DA 48 8B F9 FF 50 40 C7 43 04 0F 00 00 00
DESC: What it is: The function that writes PvP set data back to disk. When it runs: When the client saves current PvP configuration to its local files. Why you would care: Use this if you want to detect or intercept PvP set saves.
----------------------------------------
NAME: PvpSetModule_GetDataSize
SIG:  B8 42 00 00 00 C3
DESC: What it is: A helper that returns the size of the serialized PvP set data. When it runs: When the client prepares to read or write that data format. Why you would care: Use this if you need the exact saved data size for file work or validation.
----------------------------------------
NAME: PvpSetModule_GetFileVersion
SIG:  B8 00 04 00 00 C3
DESC: What it is: A helper that returns the file version used by saved PvP set data. When it runs: When the client checks or writes the saved format version. Why you would care: Use this if you need to validate or mirror the saved file format.
----------------------------------------
NAME: PvpSetModule_GetFileType
SIG:  B8 90 01 00 00 C3
DESC: What it is: A helper that returns the file-type id used by saved PvP set data. When it runs: When the client checks or writes the saved file type. Why you would care: Use this if you need the same file-type id as the client for tooling or parsing.
----------------------------------------
NAME: ShellCommandChatPvp_ExecuteCommand
SIG:  48 89 5C 24 20 56 57 41 56 48 81 EC 10 01 00 00 48 8B 05 C1 B6 ED 01 48 33 C4 48 89 84 24 00 01 00 00
DESC: What it is: The function that executes a PvP-related chat shell command such as `/pvpteam`. When it runs: When the player enters that command through chat. Why you would care: Use this if you want to react to or inspect PvP chat command handling.
----------------------------------------
NAME: ShellCommandAddPvpAction_ExecuteCommand
SIG:  40 55 41 55 48 81 EC 98 0C 00 00 48 8B 05 46 78 ED 01 48 33 C4 48 89 84 24 60 0C 00 00
DESC: What it is: The function that executes the shell command used for adding or configuring PvP actions. When it runs: When the player uses the related command through chat or command handling. Why you would care: Use this if you want to inspect or automate that PvP action command path.
----------------------------------------
CATEGORY: PvP Profile UI
----------------------------------------
NAME: PvpProfileAddon_OnSetup
SIG:  48 89 5C 24 20 55 56 57 41 54 41 55 41 56 41 57 48 81 EC D0 00 00 00 48 8B 05 5A 97 57 01
DESC: What it is: The setup function for the main PvP profile window. When it runs: When the game first builds the PvP profile UI and its child panels. Why you would care: Use this if you want a clean hook when the main PvP profile screen is created.
----------------------------------------
NAME: PvpProfileAddon_OnRequestedUpdate
SIG:  4C 8B DC 56 57 48 83 EC 68 48 8B 05 38 91 57 01 48 33 C4 48 89 44 24 40 48 8B B2 48 03 00 00
DESC: What it is: A refresh function for the main PvP profile screen. When it runs: When the game has new profile or rank data and wants the screen to redraw. Why you would care: Use this if you want a UI-side hook for profile screen updates.
----------------------------------------
NAME: PvpProfileAddon_OnRefresh
SIG:  4C 89 44 24 18 53 55 41 56 48 83 EC 70 4D 8B F0 8B EA 48 8B D9 4D 85 C0 0F 84 F3 03 00 00
DESC: What it is: A refresh function that rebuilds the visible contents of the PvP profile page. When it runs: When the game wants the current page contents to be repopulated. Why you would care: Use this if you want a hook after the profile screen has decided what to show.
----------------------------------------
NAME: PvpProfileAddon_ReceiveEvent
SIG:  40 53 56 57 48 83 EC 70 48 8B 05 19 8B 57 01 48 33 C4 48 89 44 24 60 49 8B F1 48 8B F9
DESC: What it is: The input handler for the main PvP profile window. When it runs: When the player changes tabs, presses buttons, or otherwise interacts with the profile UI. Why you would care: Use this if you want to track direct profile-window interaction.
----------------------------------------
NAME: PvpProfileAction_OnSetup
SIG:  48 8B C4 48 89 58 10 48 89 70 18 48 89 78 20 55 41 54 41 55 41 56 41 57 48 8D 68 A1
DESC: What it is: The setup function for the PvP profile action page. When it runs: When the game first builds that page inside the profile UI. Why you would care: Use this if you want a clean hook when the action page is created.
----------------------------------------
NAME: PvpProfileAction_OnRequestedUpdate
SIG:  48 8B C4 55 53 41 54 41 55 41 56 48 8D 68 A1 48 81 EC B0 00 00 00 48 89 70 D0 45 33 E4
DESC: What it is: A refresh function for the PvP profile action page. When it runs: When the game has new action or profile data for that page. Why you would care: Use this if you want a UI-side hook for action-page updates.
----------------------------------------
NAME: PvpProfileAction_ReceiveEvent
SIG:  40 55 53 56 57 41 54 41 56 41 57 48 8D 6C 24 E1 48 81 EC C0 00 00 00 48 8B 05 7A 71 57 01
DESC: What it is: The input handler for the PvP profile action page. When it runs: When the player interacts with controls on that page. Why you would care: Use this if you want to track direct action-page interaction.
----------------------------------------
NAME: PvpProfileColosseum_OnSetup
SIG:  48 8B C4 48 89 58 10 48 89 70 18 48 89 78 20 55 48 8D A8 68 FF FF FF 48 81 EC 90 01 00 00
DESC: What it is: The setup function for the Colosseum page inside the PvP profile UI. When it runs: When the game first builds that page. Why you would care: Use this if you want a clean hook when the Colosseum profile page is created.
----------------------------------------
NAME: PvpProfileColosseum_OnRequestedUpdate
SIG:  40 53 48 83 EC 20 48 8B D9 E8 F2 0D 00 00 45 33 C9 41 B0 01 48 8B CB 41 8D 51 66
DESC: What it is: A refresh function for the Colosseum page inside the PvP profile UI. When it runs: When the game wants that page to reload its current data. Why you would care: Use this if you want a UI-side hook for Colosseum profile updates.
----------------------------------------
NAME: PvpProfileColosseum_ReceiveEvent
SIG:  66 83 FA 23 0F 85 78 01 00 00 55 56 48 83 EC 78 48 8B 05 41 5F 57 01 48 33 C4 48 89 44 24 60
DESC: What it is: The input handler for the Colosseum page inside the PvP profile UI. When it runs: When the player interacts with controls on that page. Why you would care: Use this if you want to track direct Colosseum-page interaction.
----------------------------------------
NAME: PvpProfileFrontline_OnSetup
SIG:  48 8B C4 48 89 58 10 48 89 70 18 48 89 78 20 55 41 54 41 55 41 56 41 57 48 8D A8 88 FC FF FF
DESC: What it is: The setup function for the Frontline page inside the PvP profile UI. When it runs: When the game first builds that page. Why you would care: Use this if you want a clean hook when the Frontline profile page is created.
----------------------------------------
NAME: PvpProfileFrontline_OnRequestedUpdate
SIG:  48 8B 89 38 02 00 00 48 85 C9 74 0A 48 8B 01 48 FF A0 B0 00 00 00 C3
DESC: What it is: A small refresh dispatch for the Frontline page inside the PvP profile UI. When it runs: When the game requests an update for that page. Why you would care: Use this if you want a lightweight hook for Frontline profile refresh requests.
----------------------------------------
NAME: PvpProfileManeuvers_OnSetup
SIG:  48 89 5C 24 10 48 89 74 24 18 57 48 81 EC 90 00 00 00 0F 29 B4 24 80 00 00 00 48 8B 05 27 13 57 01
DESC: What it is: The setup function for the Maneuvers page inside the PvP profile UI. When it runs: When the game first builds that page. Why you would care: Use this if you want a clean hook when the Maneuvers profile page is created.
----------------------------------------
NAME: PvpProfileManeuvers_OnRequestedUpdate
SIG:  48 8B 42 08 41 B9 07 00 00 00 48 8B 10 44 8B 42 04 45 85 C0 74 1A 41 83 E8 01 74 0C
DESC: What it is: A refresh function for the Maneuvers page inside the PvP profile UI. When it runs: When the game wants that page to reload its current data. Why you would care: Use this if you want a UI-side hook for Maneuvers profile updates.
----------------------------------------
NAME: PvpProfileQuickChat_OnSetup
SIG:  48 89 5C 24 10 48 89 74 24 18 57 48 81 EC B0 00 00 00 0F 29 B4 24 A0 00 00 00 48 8B 05 77 1D 57 01
DESC: What it is: The setup function for the quick-chat page inside the PvP profile UI. When it runs: When the game first builds that page. Why you would care: Use this if you want a clean hook when the quick-chat configuration page is created.
----------------------------------------
NAME: PvpProfileQuickChat_OnRequestedUpdate
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B 82 48 03 00 00 48 8B D9 48 8B 89 38 02 00 00 48 8B 50 28
DESC: What it is: A refresh function for the quick-chat page inside the PvP profile UI. When it runs: When the game reloads stored quick-chat data into that page. Why you would care: Use this if you want a UI-side hook for quick-chat page updates.
----------------------------------------
NAME: PvpProfileQuickChat_ReceiveEvent
SIG:  48 89 5C 24 10 55 56 57 41 56 41 57 48 81 EC B0 00 00 00 48 8B 05 BE 19 57 01 48 33 C4 48 89 84 24 A0 00 00 00
DESC: What it is: The input handler for the quick-chat page inside the PvP profile UI. When it runs: When the player changes or confirms quick-chat settings on that page. Why you would care: Use this if you want to track direct quick-chat configuration interaction.
----------------------------------------
CATEGORY: PvP Utility UI
----------------------------------------
NAME: PvpActionSetView_OnSetup
SIG:  40 55 56 57 48 81 EC A0 00 00 00 48 8B 05 66 0A 57 01 48 33 C4 48 89 84 24 90 00 00 00
DESC: What it is: The setup function for the PvP action set view window. When it runs: When the game first builds that action-set UI. Why you would care: Use this if you want a clean hook when the action-set window is created.
----------------------------------------
NAME: PvpActionSetView_ReceiveEvent
SIG:  40 57 48 83 EC 60 48 8B F9 66 83 FA 21 0F 85 01 01 00 00 48 89 B4 24 80 00 00 00 48 8B B4 24 90 00 00 00
DESC: What it is: The input handler for the PvP action set view window. When it runs: When the player interacts with that UI, such as selecting or confirming an action set. Why you would care: Use this if you want to track direct action-set interaction.
----------------------------------------
NAME: PvpCalendar_OnSetup
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 41 54 41 55 41 56 41 57 48 83 EC 30
DESC: What it is: The setup function for the PvP calendar window. When it runs: When the game first builds that calendar UI. Why you would care: Use this if you want a clean hook when the PvP calendar appears.
----------------------------------------
NAME: PvpCalendar_Update
SIG:  40 53 48 83 EC 20 48 8B D9 E8 E2 C5 3E FF F6 83 A1 01 00 00 01 74 67 83 BB 00 03 00 00 00 7C 5E
DESC: What it is: The active update function for the PvP calendar window. When it runs: While the calendar is visible and the client is keeping it current. Why you would care: Use this if you want a live hook for calendar-state changes.
----------------------------------------
NAME: PvpCalendar_ReceiveEvent
SIG:  40 53 55 56 57 41 57 48 83 EC 70 48 8B 05 96 FE 56 01 48 33 C4 48 89 44 24 60 4D 8B F9
DESC: What it is: The input handler for the PvP calendar window. When it runs: When the player interacts with that calendar UI. Why you would care: Use this if you want to track direct calendar interaction.
----------------------------------------
NAME: PvpReward_OnSetup
SIG:  40 53 48 83 EC 20 BA FF FF FF FF 48 8B D9 E8 BD 8D 3E FF 48 8B CB 48 83 C4 20 5B E9
DESC: What it is: The setup function for the PvP reward window. When it runs: When the game first builds that reward UI. Why you would care: Use this if you want a clean hook when the reward window appears.
----------------------------------------
NAME: PvpReward_ReceiveEvent
SIG:  48 89 5C 24 08 57 48 83 EC 60 48 8B D9 49 8B F9 0F B7 CA 45 8B D0 83 E9 06 0F 84 A5 00 00 00
DESC: What it is: The input handler for the PvP reward window. When it runs: When the player claims rewards or navigates within that UI. Why you would care: Use this if you want to track reward interaction or claim behavior.
----------------------------------------
NAME: PvpWelcome_OnSetup
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 48 89 7C 24 20 41 54 41 56 41 57 48 83 EC 50
DESC: What it is: The setup function for the PvP welcome or tutorial window. When it runs: When the game first builds that introductory UI. Why you would care: Use this if you want a clean hook when the welcome panel appears.
----------------------------------------
NAME: PvpWelcome_ReceiveEvent
SIG:  40 53 48 83 EC 20 44 0F B7 D2 49 8B D9 41 83 EA 19 74 32 41 83 EA 2F 74 06 41 83 FA 01 75 3F
DESC: What it is: The input handler for the PvP welcome or tutorial window. When it runs: When the player confirms, advances, or otherwise interacts with that UI. Why you would care: Use this if you want to track direct interaction with the welcome flow.
----------------------------------------
CATEGORY: PvP Agent UI
----------------------------------------
NAME: AgentPvpProfile_Show
SIG:  40 53 48 81 EC 00 01 00 00 48 8B 05 78 FF 7D 01 48 33 C4 48 89 84 24 D0 00 00 00 48 8B 01
DESC: What it is: The function that shows the PvP profile agent and prepares its controller state. When it runs: When the game opens the PvP profile through the agent layer. Why you would care: Use this if you want an agent-level hook when the profile flow starts.
----------------------------------------
NAME: AgentPvpProfile_ReceiveEvent
SIG:  40 53 55 56 57 41 56 41 57 48 81 EC F8 0F 00 00 48 8B 05 D1 F8 7D 01 48 33 C4 48 89 84 24 E0 0F 00 00
DESC: What it is: The input handler for the PvP profile agent. When it runs: When UI events are routed through that agent instead of directly through the addon. Why you would care: Use this if you want an agent-level hook for PvP profile interaction.
----------------------------------------
NAME: AgentPvpProfile_Update
SIG:  48 89 5C 24 18 48 89 6C 24 20 57 48 83 EC 50 83 B9 F4 02 00 00 00 48 8B D9 0F 29 7C 24 30
DESC: What it is: The active update function for the PvP profile agent. When it runs: While the agent is active and the client is keeping its controller state current. Why you would care: Use this if you want a live hook at the agent layer instead of the addon layer.
----------------------------------------
NAME: AgentPvPMap_Show
SIG:  40 53 48 83 EC 20 48 83 79 28 00 48 8B D9 0F 85 DC 00 00 00 E8 67 E2 38 FF 4C 8B C0
DESC: What it is: The function that shows the PvP map agent and connects it to the PvP map window. When it runs: When the game opens the PvP map through the agent layer. Why you would care: Use this if you want an agent-level hook when the PvP map flow starts.
----------------------------------------
NAME: AgentPvPMap_Update
SIG:  40 57 48 83 EC 20 48 8B 41 28 48 8B F9 48 85 C0 0F 84 58 01 00 00 66 83 38 01 75 0D
DESC: What it is: The active update function for the PvP map agent. When it runs: While that agent is active and the client is keeping its controller state current. Why you would care: Use this if you want a live hook at the agent layer instead of only the map addon.
----------------------------------------
NAME: AgentPvPHeader_Show
SIG:  40 53 48 83 EC 20 48 8B D9 E8 82 30 F8 FF C7 83 30 02 00 00 01 00 00 00 48 83 C4 20 5B C3
DESC: What it is: The function that shows the PvP header agent. When it runs: When the game opens the PvP header through the agent layer. Why you would care: Use this if you want an agent-level hook when the header flow starts.
----------------------------------------
NAME: AgentPvPHeader_Update
SIG:  40 53 48 83 EC 20 83 B9 A8 0A 00 00 00 48 8B D9 75 63 48 8B 89 A0 0A 00 00 48 89 7C 24 30
DESC: What it is: The active update function for the PvP header agent. When it runs: While that agent is active and the client is refreshing its state. Why you would care: Use this if you want a live hook at the agent layer for header changes.
----------------------------------------
NAME: AgentPvPHeader_ReceiveEvent
SIG:  4C 8B DC 55 41 55 41 56 48 81 EC A0 00 00 00 48 8B 05 F2 B8 AD 01 48 33 C4 48 89 44 24 70
DESC: What it is: The input handler for the PvP header agent. When it runs: When UI callbacks or interactions are routed through that agent. Why you would care: Use this if you want an agent-level hook for PvP header interaction.
----------------------------------------
NAME: AgentPvPDuelRequest_Show
SIG:  40 53 48 83 EC 60 83 79 20 00 48 8B D9 0F 85 BA 00 00 00 48 8B 49 10 48 89 7C 24 70
DESC: What it is: The function that shows the PvP duel request agent. When it runs: When the game opens the duel request flow through the agent layer. Why you would care: Use this if you want an agent-level hook when a duel request starts.
----------------------------------------
NAME: AgentPvPDuelRequest_Update
SIG:  40 56 48 83 EC 70 48 8B 01 48 8B F1 FF 50 30 84 C0 0F 84 ?? ?? ?? ?? 48 8B 4E 10 48 8B 01
DESC: What it is: The active update function for the PvP duel request agent. When it runs: While that agent is active and the client is keeping its state current. Why you would care: Use this if you want a live hook at the agent layer for duel-request changes.
----------------------------------------
NAME: AgentPvPSpectator_Show
SIG:  48 89 5C 24 10 48 89 74 24 18 55 57 41 54 41 56 41 57 48 8B EC 48 81 EC 80 00 00 00 48 8B 05 E5 7F AD 01
DESC: What it is: The function that shows the PvP spectator agent. When it runs: When the game opens the spectator flow through the agent layer. Why you would care: Use this if you want an agent-level hook when spectating starts.
----------------------------------------
NAME: AgentPvPSpectator_Update
SIG:  40 53 56 57 48 83 EC 70 48 8B 05 B9 79 AD 01 48 33 C4 48 89 44 24 50 48 8B D9 E8 51 20 00 00
DESC: What it is: The active update function for the PvP spectator agent. When it runs: While the spectator agent is active and the client is refreshing its state. Why you would care: Use this if you want a live hook at the agent layer during spectating.
----------------------------------------
NAME: AgentPvpTeam_Show
SIG:  40 57 48 81 EC 80 00 00 00 48 8B 05 E8 9A 26 02 48 33 C4 48 89 44 24 70 48 8B 01 48 8B F9
DESC: What it is: The function that shows the PvP team-management agent. When it runs: When the game opens the team-management flow through the agent layer. Why you would care: Use this if you want an agent-level hook when team management starts.
----------------------------------------
NAME: AgentPvpTeam_ReceiveEvent
SIG:  40 53 56 41 56 48 81 EC 80 00 00 00 48 8B 05 F5 95 26 02 48 33 C4 48 89 44 24 60 48 83 BC 24 C0 00 00 00 00
DESC: What it is: The input handler for the PvP team-management agent. When it runs: When callbacks or player interaction are routed through that agent. Why you would care: Use this if you want an agent-level hook for team-management interaction.
----------------------------------------
CATEGORY: PvP Records
----------------------------------------
NAME: FrontlineRecord_OnSetup
SIG:  48 89 5C 24 10 55 56 57 41 54 41 55 41 56 41 57 48 8D 6C 24 A0 48 81 EC 60 01 00 00 48 8B 05 35 2B 67 01
DESC: What it is: The setup function for the Frontline record or history window. When it runs: When the game first builds that record UI. Why you would care: Use this if you want a clean hook when the Frontline history screen appears.
----------------------------------------
NAME: FrontlineRecord_OnRefresh
SIG:  48 89 5C 24 10 57 48 83 EC 20 F6 81 A1 01 00 00 01 49 8B F8 48 8B D9 75 0D 32 C0
DESC: What it is: A refresh function for the Frontline record or history window. When it runs: When the game reloads the data shown in that record UI. Why you would care: Use this if you want a UI-side hook for Frontline history updates.
----------------------------------------
NAME: FrontlineRecordDetail_OnSetup
SIG:  40 53 41 55 41 57 48 81 EC 90 00 00 00 48 8B 05 34 FB 66 01 48 33 C4 48 89 44 24 68 8B DA
DESC: What it is: The setup function for the Frontline record detail window. When it runs: When the game first builds the detail view for a Frontline record. Why you would care: Use this if you want a clean hook when a Frontline detail screen appears.
----------------------------------------
NAME: MKSRecord_OnSetup
SIG:  48 89 5C 24 10 55 56 57 41 54 41 55 41 56 41 57 48 8D 6C 24 B0 48 81 EC 50 01 00 00 48 8B 05 05 D0 66 01
DESC: What it is: The setup function for the Crystalline Conflict record or history window. When it runs: When the game first builds that record UI. Why you would care: Use this if you want a clean hook when the Crystalline Conflict history screen appears.
----------------------------------------
NAME: ColosseumRecord_OnSetup
SIG:  48 89 5C 24 10 55 56 57 41 54 41 55 41 56 41 57 48 8D 6C 24 80 48 81 EC 80 01 00 00 48 8B 05 95 52 67 01
DESC: What it is: The setup function for the Colosseum record or history window. When it runs: When the game first builds that record UI. Why you would care: Use this if you want a clean hook when the Colosseum history screen appears.
----------------------------------------
NAME: ManeuversHeader_OnSetup
SIG:  48 89 5C 24 10 55 56 57 41 54 41 55 41 56 41 57 48 81 EC B0 00 00 00 48 8B 05 0A B2 66 01 48 33 C4 48 89 84 24 A0 00 00 00
DESC: What it is: The setup function for the Maneuvers header window. When it runs: When the game first builds that header UI for Maneuvers mode. Why you would care: Use this if you want a clean hook when the Maneuvers header appears.
----------------------------------------
CATEGORY: Hidden PvP Internals
----------------------------------------
NAME: Hidden_ManeuversKillStreakAddon_CreateOrGet
SIG:  48 89 5C 24 10 48 89 6C 24 18 56 57 41 54 41 56 41 57 48 83 EC 30 48 8B FA 48 8B D9 E8 ?? ?? ?? ?? 4C 8B 7F 08 48 8D 15 ?? ?? ?? ?? 44 0F B7 B3
DESC: What it is: A hidden internal path that creates or reuses the Maneuvers kill-streak window. When it runs: When the game needs that hidden UI and goes through the stage manager to open it. Why you would care: Use this if you want a hook for a Maneuvers UI path that is not exposed through the obvious addon names.
----------------------------------------
NAME: UIState_IsInstanceContentUnlocked_Deep
SIG:  48 89 5C 24 08 48 89 6C 24 20 56 57 41 56 48 83 EC 20 8B F9 E8 ?? ?? ?? ?? 48 8B F0 48 85 C0 0F 84 ?? ?? ?? ?? 0F B6 88 9E 00 00 00
DESC: What it is: A deep unlock check used by the UI state system for instance content. When it runs: When the game needs to decide whether a piece of content should be treated as unlocked. Why you would care: Use this if you want a lower-level unlock gate than the visible UI functions.
----------------------------------------
NAME: UIState_IsInstanceContentCompleted_Deep
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 0F B6 F2 8B D9 E8 ?? ?? ?? ?? 48 8B F8 48 85 C0 0F 84 ?? ?? ?? ?? 0F B6 88 9E 00 00 00
DESC: What it is: A deep completion check used by the UI state system for instance content. When it runs: When the game needs to know whether a piece of content should be treated as completed. Why you would care: Use this if you want a lower-level completion gate than the visible UI layer.
----------------------------------------
NAME: UIState_UpdateMainCommands_PvPUnlockGateHelper
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 41 54 41 55 41 56 41 57 48 83 EC 20 33 FF 4C 8D 15 ?? ?? ?? ?? 44 8B DF
DESC: What it is: An internal helper that decides whether command entries should be enabled based on unlock state. When it runs: While the game updates its main command list and checks available content. Why you would care: Use this if you want to study or alter how content unlocks affect command availability.
----------------------------------------
NAME: FrontlineRecord_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 63 3D FC 00 41 B0 01 E9 CB F9 4E FF
DESC: What it is: A hidden loader path for the Frontline result UI resource. When it runs: Before the game shows the Frontline result window and needs the matching UI resource loaded. Why you would care: Use this if you want a deeper resource-level hook before the visible addon is active.
----------------------------------------
NAME: FrontlineRecordDetail_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 FB 33 FC 00 45 33 C0 E9 BB C9 4E FF
DESC: What it is: A hidden loader path for the Frontline result detail UI resource. When it runs: Before the game shows the Frontline detail result window. Why you would care: Use this if you want a deeper resource-level hook for the detail result screen.
----------------------------------------
NAME: ColosseumRecord_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 F3 56 FC 00 41 B0 01 E9 2B 21 4F FF
DESC: What it is: A hidden loader path for the Colosseum result UI resource. When it runs: Before the game shows the Colosseum result window. Why you would care: Use this if you want a deeper resource-level hook for the Colosseum result screen.
----------------------------------------
NAME: MKSRecord_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 BB 0D FC 00 45 33 C0 E9 9B 9E 4E FF
DESC: What it is: A hidden loader path for the Crystalline Conflict result UI resource. When it runs: Before the game shows the Crystalline Conflict result screen. Why you would care: Use this if you want a deeper resource-level hook before that result UI becomes visible.
----------------------------------------
NAME: PvPTeamResult_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 DB 8C BD 00 45 33 C0 E9 3B 52 08 FF
DESC: What it is: A hidden loader path for the PvP team result UI resource. When it runs: Before the game shows the team result window. Why you would care: Use this if you want a deeper resource-level hook before the visible result addon appears.
----------------------------------------
CATEGORY: PvP Resource Loaders
----------------------------------------
NAME: PvPSpectatorList_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 A3 EA DE 00 45 33 C0 E9 FB 72 31 FF
DESC: What it is: A hidden loader path for the PvP spectator list UI resource. When it runs: Before the spectator list window is shown. Why you would care: Use this if you want a resource-level hook before the visible spectator list addon appears.
----------------------------------------
NAME: PvPTeam_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 93 AC BD 00 45 33 C0 E9 2B 75 08 FF
DESC: What it is: A hidden loader path for the main PvP team UI resource. When it runs: Before the game shows the PvP team window. Why you would care: Use this if you want a resource-level hook before the visible team addon appears.
----------------------------------------
NAME: PvPTeamStatus_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 63 75 BD 00 45 33 C0 E9 FB 39 08 FF
DESC: What it is: A hidden loader path for the PvP team status UI resource. When it runs: Before the game shows the PvP team status window. Why you would care: Use this if you want a resource-level hook before the visible status addon appears.
----------------------------------------
NAME: PvPTeamActivity_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 83 7D BD 00 45 33 C0 E9 7B 42 08 FF
DESC: What it is: A hidden loader path for the PvP team activity UI resource. When it runs: Before the game shows the activity window. Why you would care: Use this if you want a resource-level hook before the visible activity addon appears.
----------------------------------------
NAME: PvPTeamInputString_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 63 9F BD 00 45 33 C0 E9 BB 67 08 FF
DESC: What it is: A hidden loader path for the PvP team text-input popup resource. When it runs: Before the game shows that popup. Why you would care: Use this if you want a resource-level hook before the visible popup appears.
----------------------------------------
NAME: PvPTeamOrganization_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 53 6D BD 00 45 33 C0 E9 AB 31 08 FF
DESC: What it is: A hidden loader path for the PvP team organization UI resource. When it runs: Before the game shows the organization window. Why you would care: Use this if you want a resource-level hook before the visible organization addon appears.
----------------------------------------
NAME: PvpWelcome_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 03 D5 E4 00 45 33 C0 E9 1B AD 37 FF
DESC: What it is: A hidden loader path for the PvP welcome or tutorial UI resource. When it runs: Before the game shows the welcome window. Why you would care: Use this if you want a resource-level hook before the visible tutorial addon appears.
----------------------------------------
NAME: PvpReward_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 2B 3B EC 00 45 33 C0 E9 5B C7 3E FF
DESC: What it is: A hidden loader path for the PvP reward UI resource. When it runs: Before the game shows the reward window. Why you would care: Use this if you want a resource-level hook before the visible reward addon appears.
----------------------------------------
NAME: PvpProfileFrontline_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 13 85 EC 00 45 33 C0 E9 0B 18 3F FF
DESC: What it is: A hidden loader path for the Frontline tab resource inside the PvP profile UI. When it runs: Before the game shows that profile tab. Why you would care: Use this if you want a resource-level hook before the visible Frontline tab appears.
----------------------------------------
NAME: PvpProfileManeuvers_LoadUldResourceHandle_Deep
SIG:  41 B9 06 00 00 00 48 8D 15 8B 52 EC 00 45 33 C0 E9 BB E1 3E FF
DESC: What it is: A hidden loader path for the Maneuvers tab resource inside the PvP profile UI. When it runs: Before the game shows that profile tab. Why you would care: Use this if you want a resource-level hook before the visible Maneuvers tab appears.
----------------------------------------
CATEGORY: PvP Team Controllers
----------------------------------------
NAME: AgentPvpTeamCrestEditor_Show_Deep
SIG:  40 53 48 83 EC 20 48 8B 01 48 8B D9 FF 50 30 48 8B CB 84 C0 74 0C 48 8B 03 48 83 C4 20 5B 48 FF 60 28
DESC: What it is: The controller-side function that shows the PvP team crest editor. When it runs: When the game opens the crest editor through its controller path. Why you would care: Use this if you want a deeper hook than the visible crest editor UI.
----------------------------------------
NAME: AgentPvpTeamCrestEditor_ReceiveEvent_Deep
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 48 89 7C 24 20 41 56 48 83 EC 30 41 8B D9 49 8B F0 4C 8B F2 48 8B F9
DESC: What it is: The input handler for the PvP team crest editor controller. When it runs: When interaction is routed through the crest editor's controller layer. Why you would care: Use this if you want to track or alter crest editor interaction below the visible addon layer.
----------------------------------------
NAME: AgentPvpTeamCrestEditor_Update_Deep
SIG:  40 53 48 83 EC 20 83 79 20 00 48 8B D9 0F 84 91 00 00 00 83 B9 98 00 00 00 01 75 7B 48 8B 49 10
DESC: What it is: The active update function for the PvP team crest editor controller. When it runs: While that controller is active and the client is keeping its state current. Why you would care: Use this if you want a live hook at the controller layer for crest editor state changes.
----------------------------------------
NAME: AgentPvpTeamInputString_Show_Deep
SIG:  40 57 48 81 EC 00 01 00 00 48 8B 05 F8 8F 26 02 48 33 C4 48 89 84 24 F0 00 00 00 4C 8B 05 BE C5 AD 01
DESC: What it is: The controller-side function that shows the PvP team text-input popup. When it runs: When the game opens that popup through its controller path. Why you would care: Use this if you want a deeper hook than the visible popup addon.
----------------------------------------
NAME: AgentPvpTeamInputString_ReceiveEvent_Deep
SIG:  48 89 5C 24 08 57 48 83 EC 40 48 8B F9 C7 02 02 00 00 00 C6 42 08 01 48 8B DA 48 8B 49 28 48 85 C9 74 2D
DESC: What it is: The input handler for the PvP team text-input controller. When it runs: When the player confirms text or triggers another callback in that popup. Why you would care: Use this if you want a controller-level hook for team text entry behavior.
----------------------------------------
NAME: AgentPvPTeamOrganization_Show_Deep
SIG:  40 53 48 83 EC 20 48 8B 01 48 8B D9 FF 50 30 84 C0 74 0F 48 8B 03 48 8B CB 48 83 C4 20 5B 48 FF 60 28
DESC: What it is: The controller-side function that shows the PvP team organization window. When it runs: When the game opens that window through its controller path. Why you would care: Use this if you want a deeper hook than the visible organization addon.
----------------------------------------
NAME: AgentPvPTeamOrganization_ReceiveEvent_Deep
SIG:  48 89 5C 24 08 48 89 74 24 10 48 89 7C 24 18 41 56 48 83 EC 20 49 8B F8 48 8B D9 44 8B 44 24 50 41 8B F1 4C 8B F2
DESC: What it is: The input handler for the PvP team organization controller. When it runs: When interaction is routed through that controller instead of directly through the addon. Why you would care: Use this if you want a controller-level hook for organization-window interaction.
----------------------------------------
NAME: AgentPvPTeamOrganization_Update_Deep
SIG:  48 89 5C 24 10 57 48 81 EC 00 01 00 00 48 8B 05 34 2D 26 02 48 33 C4 48 89 84 24 F0 00 00 00 48 8B 01 0F B6 DA 48 8B F9
DESC: What it is: The active update function for the PvP team organization controller. When it runs: While that controller is active and the client is keeping its state current. Why you would care: Use this if you want a live hook at the controller layer for organization-window state changes.
----------------------------------------
CATEGORY: PvP Directors and Map Internals
----------------------------------------
NAME: EventFramework_GetFrontlinesDirector_Deep
SIG:  48 8B 81 58 01 00 00 48 85 C0 74 1B 48 8B 88 D8 02 00 00 BA 03 80 00 00 66 39 51 02 75 09 80 B8 CE 0D 00 00 06 74 02 33 C0 C3
DESC: What it is: An EventFramework lookup that returns the active Frontline match controller when Frontline content is loaded. When it runs: It runs when the client needs to fetch the live Frontline director and first confirms that the current content type is Frontline. Why you would care: Use it as a direct path to the active Frontline director instead of walking broader framework state yourself.
----------------------------------------
NAME: GameMain_IsInFrontlineArea_Deep
SIG:  80 3D 9D F9 EB 01 12 0F 94 C0 C3
DESC: What it is: A simple game-state check that tells you whether the player is currently in a Frontline area. When it runs: It runs anywhere the client needs a fast yes or no answer about being in Frontline. Why you would care: Use it as a cheap gate before running Frontline-specific plugin logic.
----------------------------------------
NAME: EventFramework_GetRivalWingDirector_Deep
SIG:  48 8B 81 58 01 00 00 48 85 C0 74 1B 48 8B 88 D8 02 00 00 BA 03 80 00 00 66 39 51 02 75 09 80 B8 CE 0D 00 00 0C 74 02 33 C0 C3
DESC: What it is: An EventFramework lookup that returns the active Rival Wings match controller when Rival Wings content is loaded. When it runs: It runs when the client needs the live Rival Wings director and first confirms that the current content type is Rival Wings. Why you would care: Use it as a direct way to get the active Rival Wings director for plugin logic.
----------------------------------------
NAME: GameMain_IsInRivalWingsArea_Deep
SIG:  80 3D 4D F9 EB 01 27 0F 94 C0 C3
DESC: What it is: A simple game-state check that tells you whether the player is currently in a Rival Wings area. When it runs: It runs anywhere the client needs a fast yes or no answer about being in Rival Wings. Why you would care: Use it as a cheap gate before running Rival Wings-specific plugin logic.
----------------------------------------
NAME: EventFramework_GetEventMapMarkers_Deep
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 48 83 EC 20 49 8B F0 0F B7 EA 48 8B F9 E8 ?? ?? ?? ?? 84 C0 74 13 E8 ?? ?? ?? ?? 4C 8B C6 0F B7
DESC: What it is: A shared EventFramework helper that gathers map markers owned by active event or content systems. When it runs: It runs when the game needs to build or refresh event-driven markers for a map view. Why you would care: Use it if you want a broad hook for marker generation instead of chasing each content-specific marker builder separately.
----------------------------------------
NAME: FrontlineDirector_Terminate_Deep
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B F9 48 8B 0D 2C B2 EF 00 E8 57 35 7D FE 48 8B C8 48 8B D8 48 8B 10 FF 92 28 01 00 00
DESC: What it is: The shutdown path for the Frontline match controller. When it runs: It runs when the game is tearing down the active Frontline director at the end of a match or when leaving the content. Why you would care: Use it if you want to detect when Frontline state is being cleaned up.
----------------------------------------
NAME: FrontlineDirector_SetSequence_Deep
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 41 0F B6 F0 0F B6 DA 48 8B F9 E8 12 42 37 FF 80 FB 14 75 1D 40 80 FE 15 75 17
DESC: What it is: The Frontline sequence-change function that moves the match from one stage to another. When it runs: It runs when the match enters a new sequence, such as a major phase or screen-state change. Why you would care: Use it if you want a clean hook for major Frontline phase changes.
----------------------------------------
NAME: FrontlineDirector_PopulateMapMarkers_Deep
SIG:  48 8B C4 48 89 58 08 48 89 68 10 48 89 70 18 57 41 54 41 55 41 56 41 57 48 81 EC D0 00 00 00 0F 29 70 C8 48 8D 99 5C 20 00 00
DESC: What it is: The main Frontline marker builder that creates the objective markers shown on the map. When it runs: It runs when the game needs to build or refresh Frontline markers from the director's current objective data. Why you would care: Use it if you want a direct hook for Frontline objective marker output.
----------------------------------------
NAME: Frontline01_PopulateMapMarkers_Deep
SIG:  48 8B C4 48 89 58 08 66 89 50 10 55 56 57 41 54 41 55 41 56 41 57 48 8D 68 A1 48 81 EC F0 00 00 00 0F 29 70 B8 48 8D B9 94 34 00 00
DESC: What it is: A Frontline marker builder for the first Frontline ruleset. When it runs: It runs when that specific Frontline ruleset needs its map markers rebuilt. Why you would care: Use it if you want markers for that exact Frontline mode rather than the shared base path.
----------------------------------------
NAME: Frontline02_PopulateMapMarkers_Deep
SIG:  48 8B C4 57 41 54 41 55 41 56 41 57 48 81 EC E0 00 00 00 45 33 E4 49 8B F8 44 0F B7 EA 4C 8B F9 45 8B F4 44 39 A1 10 34 00 00
DESC: What it is: A Frontline marker builder for the second Frontline ruleset. When it runs: It runs when that specific Frontline ruleset needs its map markers rebuilt. Why you would care: Use it if you want a mode-specific marker hook for that Frontline variant.
----------------------------------------
NAME: Frontline03_PopulateMapMarkers_Deep
SIG:  48 8B C4 48 89 58 08 48 89 68 10 48 89 70 18 57 41 54 41 55 41 56 41 57 48 81 EC D0 00 00 00 0F 29 70 C8 4C 8D B9 F4 34 00 00
DESC: What it is: A Frontline marker builder for the third Frontline ruleset. When it runs: It runs when that specific Frontline ruleset needs its markers rebuilt. Why you would care: Use it if you want a marker hook tied to that exact Frontline mode.
----------------------------------------
NAME: Frontline04_PopulateMapMarkers_Deep
SIG:  48 8B C4 48 89 58 18 66 89 50 10 48 89 48 08 55 56 57 41 54 41 55 41 56 41 57 48 8D 68 A1 48 81 EC 00 01 00 00 0F 29 70 B8 48 8D 99 A4 34 00 00
DESC: What it is: A Frontline marker builder for the fourth Frontline ruleset. When it runs: It runs when that specific Frontline ruleset needs its markers rebuilt. Why you would care: Use it if you want a marker hook tied to that exact Frontline mode instead of the shared path.
----------------------------------------
NAME: RivalWingDirector_Terminate_Deep
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B D9 48 8B 0D DC 12 EA 00 E8 07 96 77 FE 48 8B F8 48 85 C0 74 57 48 8B 10 48 8B C8 FF 92 28 01 00 00
DESC: What it is: The shutdown path for the Rival Wings match controller. When it runs: It runs when the game is tearing down the active Rival Wings director at the end of a match or when leaving the content. Why you would care: Use it if you want to detect when Rival Wings state is being cleaned up.
----------------------------------------
NAME: RivalWingDirector_PopulateMapMarkers_Deep
SIG:  48 8B C4 48 89 58 08 48 89 70 10 48 89 78 18 55 41 54 41 55 41 56 41 57 48 8D 68 A1 48 81 EC D0 00 00 00 41 BE 30 00 00 00 0F 29 70 C8 41 8B F6
DESC: What it is: The main Rival Wings marker builder that creates the objective markers shown on the map. When it runs: It runs when the game needs to build or refresh Rival Wings map markers from the director's live objective data. Why you would care: Use it if you want a direct hook for Rival Wings objective marker output.
----------------------------------------
CATEGORY: PvP Director Vtable Methods
----------------------------------------
NAME: FrontlineDirector_vf319_Deep
SIG:  48 83 EC 28 45 33 C9 45 33 C0 33 D2 E8 ?? ?? ?? ?? 32 C0 48 83 C4 28 C3
DESC: What it is: A hidden Frontline director function that clears or resets part of the match state. When it runs: It runs when the Frontline director needs to wipe or rebuild one of its internal state blocks. Why you would care: Use it if you want to catch resets or reinitialization of Frontline state without hooking the larger update logic.
----------------------------------------
NAME: FrontlineDirector_vf281_Deep
SIG:  48 83 EC 28 8B 81 D8 1F 00 00 83 F8 03 73 2C 48 C1 E0 05 0F B6 94 08 D0 24 00 00 80 FA 03 73 1B 8B 94 91 30 25 00 00 85 D2 74 10 E8 80 AA 34 FF 84 C0 74 07 B0 01
DESC: What it is: A hidden Frontline check that tests whether the current internal objective state matches a valid condition. When it runs: It runs when the director needs a yes or no answer about the current team or objective slot. Why you would care: Use it if you want a deeper state check than the usual UI updates and want to detect when Frontline logic considers an objective condition satisfied.
----------------------------------------
NAME: FrontlineDirector_vf375_Deep
SIG:  48 83 EC 28 8B 81 D8 1F 00 00 83 F8 03 73 2C 48 C1 E0 05 0F B6 94 08 D0 24 00 00 80 FA 03 73 1B 8B 94 91 30 25 00 00 85 D2 74 10 E8 60 A9 34 FF 84 C0 74 07 32 C0
DESC: What it is: A hidden Frontline check paired with `vf281` that tests the same state but answers the opposite question. When it runs: It runs anywhere the director needs the inverse result of the same objective or team-state test. Why you would care: Use it if you want both sides of the same internal Frontline condition instead of recreating the logic yourself.
----------------------------------------
NAME: FrontlineDirector_vf320_Deep
SIG:  40 53 48 83 EC 20 48 89 6C 24 30 48 8B D9 48 89 7C 24 40 BD 30 00 00 00 4C 89 74 24 48 48 8D B9 54 20 00 00 41 BE 00 00 00 E0
DESC: What it is: A hidden Frontline update function that keeps match state, map state, and timers current while the match is running. When it runs: It runs repeatedly during active Frontline play as part of the director's normal update cycle. Why you would care: Use it if you want one broad hook for live Frontline state changes instead of several smaller UI-specific hooks.
----------------------------------------
NAME: FrontlineDirector_vf378_Deep
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 30 8D 42 FD 41 8B F1 41 8B F8 48 8B D9 83 F8 06 0F 87 F3 04 00 00 48 8D 0D 95 14 70 FE
DESC: What it is: A large hidden Frontline handler that processes many different match events in one place. When it runs: It runs when the Frontline director receives important state changes such as score updates, objective ownership changes, or internal reset events. Why you would care: Use it if you want a powerful hook that sees most major Frontline match changes before they are spread out to smaller systems.
----------------------------------------
NAME: FrontlineDirector_vf385_Deep
SIG:  4C 8B DC 55 56 48 8B EC 48 83 EC 78 48 8B 05 25 79 ED 00 48 33 C4 48 89 45 E8 8B 81 C4 33 00 00 48 8B F1 D1 E8 A8 01 0F 85 E5 04 00 00
DESC: What it is: A hidden Frontline text and UI refresh helper that prepares display data for objectives and match information. When it runs: It runs after the director decides the visible Frontline UI needs to be rebuilt or refreshed. Why you would care: Use it if you want a hook close to the moment when Frontline text and objective displays are being prepared for the screen.
----------------------------------------
NAME: RivalWingDirector_vf252_Deep
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 48 83 EC 30 48 8B 02 48 8B E9 48 8B CA 41 0F B7 F9 41 0F B7 F0 48 8B DA FF 50 10 83 F8 07 75 3B
DESC: What it is: A hidden Rival Wings object handler that treats one specific object pattern differently from the normal path. When it runs: It runs when Rival Wings processes certain event objects and decides whether they need special handling. Why you would care: Use it if you want to catch special object behavior in Rival Wings that does not follow the normal generic object flow.
----------------------------------------
NAME: RivalWingDirector_vf289_Deep
SIG:  40 53 48 83 EC 20 49 8B 08 49 8B D8 48 89 74 24 30 48 89 7C 24 38 49 8B F9 4C 89 74 24 40 4C 8B F2 48 85 C9 74 4E 48 8B 01 FF 50 10
DESC: What it is: A hidden Rival Wings helper that tries to turn generic object references into more useful live character references. When it runs: It runs when the director needs to work with objects that may actually represent active battle characters. Why you would care: Use it if you want a deeper hook for figuring out which objects in Rival Wings map back to real combat actors.
----------------------------------------
NAME: RivalWingDirector_vf290_Deep
SIG:  40 53 48 83 EC 20 48 8B 02 48 8B CA 48 8B DA FF 50 10 83 F8 02 75 32 48 8B 03 48 8B CB FF 50 10 83 F8 02 75 0D 0F B6 83 91 00 00 00
DESC: What it is: A hidden Rival Wings helper that does the same kind of object-to-character conversion as `vf289`, but for one object at a time. When it runs: It runs when the director needs to resolve a single object reference into a real combat object. Why you would care: Use it if you want a smaller, more focused hook for object normalization inside Rival Wings.
----------------------------------------
NAME: RivalWingDirector_vf319_Deep
SIG:  40 53 48 83 EC 30 44 8B 81 E8 1F 00 00 41 B9 01 00 00 00 BA A2 02 00 00 C7 44 24 20 A2 02 00 00 48 8B D9 E8 18 D0 31 FF 48 89 83 F0 1F 00 00
DESC: What it is: A hidden Rival Wings helper that looks up and stores a specific internal object reference for later use. When it runs: It runs when the director needs to acquire or refresh one of its cached internal handles. Why you would care: Use it if you want to track when Rival Wings refreshes important internal object references behind the scenes.
----------------------------------------
NAME: RivalWingDirector_vf320_Deep
SIG:  40 53 48 83 EC 50 0F 29 74 24 40 48 8B D9 0F 29 7C 24 30 44 0F 29 44 24 20 E8 02 CE F8 FF 48 8B 05 8B 0E EA 00 48 8B CB
DESC: What it is: A hidden Rival Wings update function that keeps the match state and visible match messaging current while the match is active. When it runs: It runs repeatedly during Rival Wings as part of the director's main update cycle. Why you would care: Use it if you want one broad hook for live Rival Wings state instead of chasing several smaller announcement and timer helpers.
----------------------------------------
NAME: RivalWingDirector_vf378_Deep
SIG:  40 55 53 56 57 41 54 41 55 41 56 41 57 48 8D 6C 24 E8 48 81 EC 18 01 00 00 48 8B 05 08 DC E7 00 48 33 C4 48 89 45 D0 44 8B BD 80 00 00 00
DESC: What it is: A large hidden Rival Wings handler that processes many different match events and pushes the results into the director's state. When it runs: It runs when major Rival Wings events happen, including score changes, objective updates, text changes, and other match-wide transitions. Why you would care: Use it if you want a single high-value hook that sees most major Rival Wings event traffic.
----------------------------------------
NAME: RivalWingDirector_vf392_Deep
SIG:  48 83 EC 28 85 D2 74 07 32 C0 48 83 C4 28 C3 E8 6C 20 00 00 B0 01 48 83 C4 28 C3
DESC: What it is: A hidden Rival Wings helper that only runs a refresh path when a specific flag allows it. When it runs: It runs when Rival Wings needs to decide whether a refresh action should happen or be skipped. Why you would care: Use it if you want to understand or intercept the gate that decides whether a Rival Wings refresh step is allowed to proceed.
----------------------------------------
NAME: RivalWingDirector_vf399_Deep
SIG:  40 53 48 83 EC 20 48 8B D9 E8 62 8C 31 FF 3C 17 75 08 32 C0 48 83 C4 20 5B C3 48 8B CB 48 83 C4 20 5B E9 E9 FD F8 FF
DESC: What it is: A hidden Rival Wings state check that blocks normal inherited behavior during one specific match phase. When it runs: It runs whenever the director needs to know whether that special phase is active before continuing. Why you would care: Use it if you want a clean gate for one of Rival Wings' special internal phases.
----------------------------------------
NAME: RivalWingDirector_vf404_Deep
SIG:  48 83 EC 28 48 8B 0D 55 06 EA 00 E8 80 89 77 FE 48 85 C0 74 2C 48 8B 10 48 8B C8 FF 92 28 01 00 00 48 8B C8 BA 19 01 00 00 E8 52 3D B2 FE
DESC: What it is: A hidden Rival Wings path that opens a related game window or controller through the agent system. When it runs: It runs when the game wants to show that Rival Wings interface on demand. Why you would care: Use it if you want a reliable hook for when that hidden Rival Wings UI is opened.
----------------------------------------
CATEGORY: Crystalline Conflict State
----------------------------------------
NAME: GameMain_IsInCrystallineConflictArea_Deep
SIG:  0F B6 05 7D F9 EB 01 3C 2A 77 13 48 B9 00 00 00 10 20 04 00 00 48 0F A3 C1 73 03 B0 01 C3 32 C0
DESC: What it is: A game-state check that tells you whether the player is currently in a Crystalline Conflict area. When it runs: It runs anywhere the client needs a direct yes or no answer about being in Crystalline Conflict. Why you would care: Use it as a simple gate before running any Crystalline Conflict-specific logic in a plugin.
----------------------------------------
NAME: ContentFinderCondition_IsCrystallineConflict_Deep
SIG:  40 53 48 83 EC 20 48 8B D9 0F B7 49 08 E8 6E ED CC FF 80 78 6D 1D 74 16 48 8B 03 48 8B CB FF 90 98 00 00 00 84 C0 75 06
DESC: What it is: A content-finder check that decides whether a selected duty entry belongs to Crystalline Conflict. When it runs: It runs when the client needs to classify a duty or queue entry as Crystalline Conflict or not. Why you would care: Use it if you want to identify Crystalline Conflict duties from the duty finder side instead of only checking the live territory.
----------------------------------------
NAME: ContentFinderCondition_GetCrystallineConflictGameplayFeatureCount_Deep
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 0F B7 49 08 E8 98 E1 CC FF 48 8B F0 8B 48 5C 85 C9 74 30
DESC: What it is: A helper that returns how many Crystalline Conflict gameplay-feature entries are attached to a duty-finder record. When it runs: It runs when the client is building or checking the extra gameplay-feature data linked to a Crystalline Conflict duty. Why you would care: Use it if you want to inspect how many special Crystalline Conflict feature rows a duty exposes.
----------------------------------------
NAME: ContentFinderCondition_GetCrystallineConflictGameplayFeatureAddonId_Deep
SIG:  48 83 EC 28 0F B7 49 08 E8 13 E1 CC FF 33 C9 BA 02 00 00 00 80 78 6D 1E 0F 44 CA 8B C1 48 83 C4 28 C3
DESC: What it is: A helper that resolves the visible feature or addon id for a Crystalline Conflict gameplay-feature entry. When it runs: It runs when the client needs to turn stored gameplay-feature data into something the UI can show or use. Why you would care: Use it if you want to connect Crystalline Conflict feature records to the ids the UI actually works with.
----------------------------------------
NAME: EventFramework_GetCrystallineConflictDirector_Deep
SIG:  48 8B 81 58 01 00 00 48 85 C0 74 1B 48 8B 88 D8 02 00 00 BA 03 80 00 00 66 39 51 02 75 09 80 B8 CE 0D 00 00 05 74 02 33 C0 C3
DESC: What it is: An EventFramework lookup that returns the active Crystalline Conflict match controller if one is currently loaded. When it runs: It runs when the client needs to fetch the live Crystalline Conflict director and first makes sure the current content really is Crystalline Conflict. Why you would care: Use it as a direct path to the live Crystalline Conflict director instead of finding it indirectly through broader framework state.
----------------------------------------
NAME: GetInstanceContentCrystallineConflictDirector_Deep
SIG:  48 83 EC 28 48 83 3D FC D4 06 01 00 74 11 E8 6D 53 30 FF 48 8B C8 48 83 C4 28 E9 51 25 31 FF 33 C0
DESC: What it is: A small global helper that returns the current Crystalline Conflict director or gives back nothing if it is unavailable. When it runs: It runs whenever code wants a quick way to fetch the current Crystalline Conflict director. Why you would care: Use it as an easy hook or lookup point when you only need the live director and do not want to walk through EventFramework yourself.
----------------------------------------
CATEGORY: Crystalline Conflict Director Methods
----------------------------------------
NAME: CrystallineConflictDirector_Terminate_Deep
SIG:  48 89 5C 24 10 48 89 6C 24 18 56 57 41 56 48 81 EC A0 00 00 00 48 8B 05 9C CF E5 00 48 33 C4 48 89 84 24 90 00 00 00 4C 8B F1
DESC: What it is: The shutdown path for the Crystalline Conflict match controller. When it runs: It runs when the game is cleaning up the active Crystalline Conflict director at the end of a match or when leaving the content. Why you would care: Use it if you want to detect or hook the moment Crystalline Conflict state is being torn down.
----------------------------------------
NAME: CrystallineConflictDirector_SetSequence_Deep
SIG:  48 89 6C 24 10 48 89 74 24 18 57 48 83 EC 20 41 0F B6 F8 0F B6 F2 48 8B E9 80 FA 14 74 5A 41 80 F8 14 75 4E
DESC: What it is: The Crystalline Conflict sequence-change function that moves the match from one stage to another. When it runs: It runs when the match enters a new sequence, such as a major phase change or screen-state transition. Why you would care: Use it if you want a clean hook for major Crystalline Conflict phase changes instead of trying to infer them from many smaller updates.
----------------------------------------
NAME: CrystallineConflictDirector_vf323_Deep
SIG:  48 89 5C 24 08 57 48 83 EC 20 E8 A1 1B F7 FF 48 8B 0D 4A FE E7 00 E8 75 81 75 FE 48 8B C8 48 8B F8 48 8B 10 FF 92 28 01 00 00
DESC: What it is: A hidden Crystalline Conflict setup follow-up that refreshes related UI and agent state after the main setup finishes. When it runs: It runs shortly after the base setup path completes and the game wants to make sure dependent UI pieces are updated. Why you would care: Use it if you want a hook close to the first full refresh after Crystalline Conflict has been set up.
----------------------------------------
NAME: CrystallineConflictDirector_vf380_Deep
SIG:  48 89 5C 24 18 55 48 8B EC 48 81 EC 80 00 00 00 48 8B 1D 09 56 05 01 48 85 DB 0F 84 8E 01 00 00 0F 57 C0
DESC: What it is: A hidden Crystalline Conflict helper that shows or queues one of the match screen images or banner displays. When it runs: It runs when the game wants to present that large Crystalline Conflict screen image at the correct moment. Why you would care: Use it if you want to detect or react to those larger on-screen presentation moments instead of only the lower-level match state.
----------------------------------------
NAME: CrystallineConflictDirector_vf320_Deep
SIG:  40 53 56 57 48 83 EC 20 48 8B 05 51 FA E7 00 33 FF 4C 8B 81 E8 1F 00 00 48 BB 07 69 90 06 69 90 06 69
DESC: What it is: A hidden Crystalline Conflict update function that keeps match data, timers, names, and visible state current while the match is active. When it runs: It runs repeatedly during live Crystalline Conflict as part of the director's main update cycle. Why you would care: Use it if you want one broad hook for ongoing Crystalline Conflict state changes.
----------------------------------------
NAME: CrystallineConflictDirector_vf378_Deep
SIG:  40 55 53 57 41 54 41 56 41 57 48 8D AC 24 08 FF FF FF 48 81 EC F8 01 00 00 48 8B 05 18 C7 E5 00 48 33 C4
DESC: What it is: A large hidden Crystalline Conflict handler that processes many different match events in one place. When it runs: It runs when major Crystalline Conflict events happen, including phase changes, roster updates, object-related changes, and screen-display updates. Why you would care: Use it if you want one high-value hook that sees most major Crystalline Conflict event traffic.
----------------------------------------
NAME: CrystallineConflictDirector_vf287_Deep
SIG:  48 89 5C 24 08 44 8B DA 48 8B D9 81 FA 00 00 00 E0 74 50 48 8B 89 E8 1F 00 00 48 B8 07 69 90 06 69 90 06 69
DESC: What it is: A hidden Crystalline Conflict roster lookup that finds a tracked participant by entity id and returns one small state value for that entry. When it runs: It runs when the director needs a fast lookup into its cached participant list. Why you would care: Use it if you want to track or inspect per-player state held inside the Crystalline Conflict roster cache.
----------------------------------------
NAME: CrystallineConflictDirector_vf281_Deep
SIG:  48 83 EC 28 F6 81 EA 20 00 00 01 74 10 E8 5E 7E 2F FF 3C 15 75 07 B0 01 48 83 C4 28 C3
DESC: What it is: A hidden Crystalline Conflict phase check that returns true only during one specific internal match state. When it runs: It runs whenever the director needs to know whether that special phase is currently active. Why you would care: Use it if you want a clean boolean gate for that particular Crystalline Conflict phase.
----------------------------------------
NAME: CrystallineConflictDirector_vf375_Deep
SIG:  48 83 EC 28 F6 81 EA 20 00 00 01 74 10 E8 2E 7E 2F FF 3C 15 75 07 32 C0 48 83 C4 28 C3 B0 01
DESC: What it is: A hidden Crystalline Conflict phase check paired with `vf281` that answers the opposite question. When it runs: It runs anywhere the director needs the inverse result of the same special phase test. Why you would care: Use it if you want both sides of the same internal phase gate without rebuilding the condition yourself.
----------------------------------------
NAME: CrystallineConflictDirector_vf399_Deep
SIG:  40 53 48 83 EC 20 48 8B D9 E8 02 7E 2F FF 3C 17 75 08 32 C0 48 83 C4 20 5B C3 48 8B CB 48 83 C4 20 5B E9 89 EF F6 FF
DESC: What it is: A hidden Crystalline Conflict state check that blocks the normal inherited behavior during one specific internal phase. When it runs: It runs whenever the director needs to decide whether that phase should suppress the normal path. Why you would care: Use it if you want a simple gate for that special Crystalline Conflict phase and the behavior it disables.
----------------------------------------
NAME: CrystallineConflictDirector_vf252_Deep
SIG:  48 89 5C 24 18 55 56 57 48 83 EC 30 48 8B 02 48 8B F9 48 8B CA 41 0F B7 E9 41 0F B7 F0 48 8B DA FF 50 10 83 F8 07 0F 85 CF 00 00 00
DESC: What it is: A hidden Crystalline Conflict object handler that updates certain match objects before handing them back to the normal path. When it runs: It runs when the director processes certain event or interactable objects that need special Crystalline-specific handling. Why you would care: Use it if you want a hook for map objects or pickups that are treated differently from ordinary world objects.
----------------------------------------
NAME: CrystallineConflictDirector_vf404_Deep
SIG:  40 53 48 83 EC 20 88 15 C8 11 05 01 48 8B D9 48 8B 01 FF 90 88 0C 00 00 48 8B CB 48 83 C4 20 5B E9 4B A9 2F FF
DESC: What it is: A hidden Crystalline Conflict toggle path that flips one global state value and then forces a refresh. When it runs: It runs when the game changes that global Crystalline Conflict state and wants the director and UI to update immediately. Why you would care: Use it if you want a hook for a clean state toggle that is followed by a visible refresh.
----------------------------------------
NAME: CrystallineConflictDirector_vf319_Deep
SIG:  48 83 EC 38 44 0F B6 81 D0 0D 00 00 BA 3A 02 00 00 41 B9 01 00 00 00 C7 44 24 20 00 00 00 00 E8 1C B1 2F FF 32 C0
DESC: What it is: A hidden Crystalline Conflict helper that sends or triggers a director-side message based on one stored byte of state. When it runs: It runs when the director needs to issue that specific internal message or notification. Why you would care: Use it if you want a narrow hook for one distinct internal Crystalline Conflict message path.
----------------------------------------
CATEGORY: Crystalline Conflict UI
----------------------------------------
NAME: PvPMKSBattleLog_OnSetup_Deep
SIG:  48 89 5C 24 08 48 89 74 24 10 48 89 7C 24 18 4C 89 74 24 20 41 57 48 83 EC 20 48 8B D9 49 8D 48 10
DESC: What it is: The setup function for the Crystalline Conflict battle log window. When it runs: It runs when the battle log is first being created and connected to its UI resources. Why you would care: Use it if you want a clean hook for the moment the battle log window is first built.
----------------------------------------
NAME: PvPMKSBattleLog_OnRefresh_Deep
SIG:  48 89 5C 24 10 48 89 74 24 18 57 48 83 EC 20 F6 81 A1 01 00 00 01 49 8B F0 8B FA 48 8B D9 0F 84 91 01 00 00
DESC: What it is: The refresh function for the Crystalline Conflict battle log window. When it runs: It runs when the game wants to redraw the battle log with the newest match event data. Why you would care: Use it if you want to react when the visible battle log content changes.
----------------------------------------
NAME: PvPMKSBattleLog_OnRequestedUpdate_Deep
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B 82 A8 03 00 00 48 8B D9 4D 8B 88 48 03 00 00 48 8B 48 28 8B B9 60 09 00 00
DESC: What it is: A helper that decides whether the Crystalline Conflict battle log needs to update. When it runs: It runs when outside state changes suggest the battle log may need a new refresh. Why you would care: Use it if you want to catch update requests before the full visible redraw happens.
----------------------------------------
NAME: PvPMKSHeader_OnRefresh_Deep
SIG:  48 89 5C 24 08 57 48 83 EC 20 F6 81 A1 01 00 00 01 49 8B D8 48 8B F9 74 2C 85 D2 74 28 48 85 DB 74 23
DESC: What it is: The refresh function for the main Crystalline Conflict header at the top of the screen. When it runs: It runs when the game wants to redraw the visible header text or indicators. Why you would care: Use it if you want a hook for visible match-state updates in the main header.
----------------------------------------
NAME: PvPMKSHeader_OnRequestedUpdate_Deep
SIG:  48 89 5C 24 18 55 56 57 41 54 41 55 41 56 41 57 48 83 EC 40 4C 8B B2 A8 03 00 00 33 ED 4D 8B A8 48 03 00 00
DESC: What it is: A helper that decides whether the Crystalline Conflict header needs to refresh. When it runs: It runs when match data changes and the game needs to decide if the visible header should be updated. Why you would care: Use it if you want a lighter hook before the full header refresh runs.
----------------------------------------
NAME: PvPMKSIntroduction_Initialize_Deep
SIG:  48 89 5C 24 20 55 48 83 EC 20 4C 89 74 24 40 48 8B E9 E8 79 CC 31 FF E8 D4 9B D5 FE 33 D2 4C 8B C0
DESC: What it is: The initialize function for the Crystalline Conflict introduction screen. When it runs: It runs when the introduction screen is being prepared and its internal state is being created. Why you would care: Use it if you want a hook for the earliest setup stage of the introduction screen.
----------------------------------------
NAME: PvPMKSIntroduction_LoadUldResourceHandle_Deep
SIG:  48 89 5C 24 10 48 89 6C 24 18 56 57 41 54 41 56 41 57 48 83 EC 40 48 8B 05 2B 03 4A 01 48 33 C4
DESC: What it is: The resource-loading function for the Crystalline Conflict introduction screen. When it runs: It runs when the game loads the UI file and other resources used by that screen. Why you would care: Use it if you want a hook tied to the actual loading of the introduction UI assets.
----------------------------------------
NAME: PvPMKSIntroduction_IsFullyLoaded_Deep
SIG:  40 53 48 83 EC 20 48 8B D9 E8 32 D2 31 FF 84 C0 74 39 48 8B 93 48 02 00 00 33 C0 0F 1F 44 00 00
DESC: What it is: A readiness check for the Crystalline Conflict introduction screen. When it runs: It runs when the game wants to know whether all required UI resources have finished loading. Why you would care: Use it if you need to wait until the introduction screen is fully ready before reading or changing anything.
----------------------------------------
NAME: PvPMKSIntroduction_Update_Deep
SIG:  40 53 48 83 EC 30 8B 81 50 02 00 00 48 8B D9 0F 29 74 24 20 0F 28 F1 83 F8 02 75 44
DESC: What it is: The repeating update function for the Crystalline Conflict introduction screen. When it runs: It runs while that screen is open to advance timers, transitions, and other live UI state. Why you would care: Use it if you want a live hook for the introduction screen while it is active.
----------------------------------------
NAME: PvPMKSIntroduction_OnRefresh_Deep
SIG:  40 53 48 83 EC 20 48 8B D9 E8 42 04 00 00 BA 01 00 00 00 48 8B CB E8 95 DC 31 FF 48 85 C0 74 0D
DESC: What it is: The refresh function for the Crystalline Conflict introduction screen. When it runs: It runs after loading or after state changes when the game wants to redraw the visible contents of the screen. Why you would care: Use it if you want to react when the introduction screen content changes.
----------------------------------------
NAME: PvPMKSIntroduction_ReceiveEvent_Deep
SIG:  66 83 FA 4A 75 66 48 89 5C 24 08 57 48 83 EC 20 41 F6 41 2A 01 49 8B F9 48 8B D9 75 45
DESC: What it is: The input handler for the Crystalline Conflict introduction screen. When it runs: It runs when the player presses buttons or closes or advances the introduction screen. Why you would care: Use it if you want to catch direct player interaction with that screen.
----------------------------------------
NAME: PvPMKSRankRating_LoadUldResourceHandle_Deep
SIG:  48 89 5C 24 10 48 89 6C 24 18 48 89 74 24 20 57 41 54 41 55 41 56 41 57 48 81 EC 90 00 00 00 48 8B 05 A2 F5 49 01
DESC: What it is: The resource-loading function for the Crystalline Conflict rank-rating screen. When it runs: It runs when the game loads the UI file and related assets for that rating screen. Why you would care: Use it if you want a hook that fires when the rank-rating screen resources are being loaded.
----------------------------------------
NAME: PvPMKSRankRating_IsFullyLoaded_Deep
SIG:  40 53 48 83 EC 20 48 8B D9 E8 12 C4 31 FF 84 C0 74 39 48 8D 93 58 04 00 00 33 C0 0F 1F 44 00 00
DESC: What it is: A readiness check for the Crystalline Conflict rank-rating screen. When it runs: It runs when the game needs to know whether that screen has finished loading all required resources. Why you would care: Use it if you need to wait until the screen is fully ready before doing plugin work against it.
----------------------------------------
NAME: PvPMKSRankRating_Update_Deep
SIG:  40 53 48 83 EC 30 0F 29 74 24 20 48 8B D9 0F 28 F1 E8 FA BD 31 FF 80 BB 34 03 00 00 00 74 21
DESC: What it is: The repeating update function for the Crystalline Conflict rank-rating screen. When it runs: It runs while the rating screen is open to advance live state such as transitions and display timing. Why you would care: Use it if you want a live hook while that rating screen is active.
----------------------------------------
NAME: PvPMKSRankRating_OnRefresh_Deep
SIG:  40 53 48 83 EC 20 48 8B D9 85 D2 7E 25 49 8B C8 E8 5B 00 2E FF 84 C0 74 19 48 8B 8B 40 03 00 00 BA 69 00 00 00
DESC: What it is: The refresh function for the Crystalline Conflict rank-rating screen. When it runs: It runs when the game wants to redraw the visible rank or rating information. Why you would care: Use it if you want a hook for when the displayed rating data changes.
----------------------------------------
NAME: PvPMKSRankRating_ReceiveEvent_Deep
SIG:  48 89 5C 24 08 57 48 83 EC 20 49 8B F9 48 8B D9 66 83 FA 09 74 7A 66 83 FA 0F 74 1D 66 83 FA 4A 75 63
DESC: What it is: The input handler for the Crystalline Conflict rank-rating screen. When it runs: It runs when the player interacts with or closes that screen. Why you would care: Use it if you want to react to direct player input on the rank-rating screen.
----------------------------------------
CATEGORY: Crystalline Conflict Agents and Records
----------------------------------------
NAME: AgentPvPMKSIntroduction_ReceiveEvent_Deep
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 48 8B D9 48 8B FA 49 8B C8 40 32 F6 E8 20 41 91 FF 44 8D 40 02
DESC: What it is: The agent-side input handler for the Crystalline Conflict introduction flow. When it runs: It runs when the game passes introduction screen events through the agent layer before they reach the addon. Why you would care: Use it if you want an earlier hook than the addon itself for introduction-screen input.
----------------------------------------
NAME: AgentPvPMKSIntroduction_Hide_Deep
SIG:  40 53 48 83 EC 20 48 8B D9 E8 E2 7C 76 FF 48 8B 4B 28 48 85 C9 74 13 48 8B 01 BA 01 00 00 00 FF 50 10
DESC: What it is: The hide function for the Crystalline Conflict introduction agent. When it runs: It runs when the game closes that introduction flow and tears down the current agent-side view or task. Why you would care: Use it if you want to detect when the introduction flow is being dismissed.
----------------------------------------
NAME: AgentPvPMKSIntroduction_Update_Deep
SIG:  48 89 6C 24 18 56 48 83 EC 40 48 8B 01 8B EA 48 8B F1 FF 50 30 84 C0 0F 84 ED 00 00 00 48 89 5C 24 50
DESC: What it is: The repeating update function for the Crystalline Conflict introduction agent. When it runs: It runs while the introduction flow is active to keep the agent-side state current. Why you would care: Use it if you want a live hook on the controller layer instead of only the UI layer.
----------------------------------------
NAME: AgentPvPMKSRankRating_ReceiveEvent_Deep
SIG:  40 53 55 56 57 41 54 41 56 41 57 48 81 EC D0 00 00 00 48 8B 05 AF AB B1 01 48 33 C4 48 89 84 24 C0 00 00 00
DESC: What it is: The agent-side input handler for the Crystalline Conflict rank-rating flow. When it runs: It runs when the game routes confirmation or close actions through the agent layer before the addon handles them. Why you would care: Use it if you want an earlier hook than the addon for rank-rating input.
----------------------------------------
NAME: AgentPvPMKSRankRating_Hide_Deep
SIG:  40 53 48 83 EC 50 48 8B 01 48 8B D9 FF 50 30 84 C0 74 6B 48 8B 4B 18 48 85 C9 74 4C C7 44 24 30 03 00 00 00
DESC: What it is: The hide function for the Crystalline Conflict rank-rating agent. When it runs: It runs when the rating flow is being closed and the current agent-side task state is being released. Why you would care: Use it if you want to detect when the rank-rating flow is being dismissed.
----------------------------------------
NAME: AgentPvPMKSRankRating_Update_Deep
SIG:  40 53 48 83 EC 40 48 8B D9 48 8B 49 28 48 85 C9 74 6F 83 B9 F4 01 00 00 01 75 66 48 8B 53 10
DESC: What it is: The repeating update function for the Crystalline Conflict rank-rating agent. When it runs: It runs while the rating flow is active to keep the controller-side state current. Why you would care: Use it if you want a live agent-layer hook while that flow is on screen.
----------------------------------------
NAME: MKSRecord_OnRefresh_Deep
SIG:  48 89 6C 24 18 56 48 83 EC 20 F6 81 A1 01 00 00 01 49 8B F0 48 8B E9 75 0D 32 C0 48 8B 6C 24 40 48 83 C4 20 5E C3
DESC: What it is: The refresh function for the Crystalline Conflict record or history screen. When it runs: It runs when the game wants to redraw the visible record data from stored match results. Why you would care: Use it if you want to react when the history screen content changes.
----------------------------------------
NAME: MKSRecord_ReceiveEvent_Deep
SIG:  66 83 FA 19 0F 85 33 01 00 00 48 89 5C 24 08 57 48 83 EC 40 48 8B F9 41 8B D8 49 8B C9 33 D2 E8 1C 63 4B FF
DESC: What it is: The input handler for the Crystalline Conflict record or history screen. When it runs: It runs when the player interacts with that record screen. Why you would care: Use it if you want to track direct input on the history UI.
----------------------------------------
NAME: MKSRecord_HandleCustomInput_Deep
SIG:  40 53 48 83 EC 30 80 7A 04 00 48 8B D9 75 46 83 3A 02 75 41 48 8B 91 50 02 00 00 45 33 C9 41 B0 01
DESC: What it is: A helper that handles controller-style or custom input for the Crystalline Conflict record screen. When it runs: It runs when that screen receives non-mouse input paths that need special handling. Why you would care: Use it if you want to catch controller or alternate input separately from normal click handling.
----------------------------------------
NAME: MKSRecord_OnOpenTransitionStarted_Deep
SIG:  40 53 48 83 EC 20 48 8B D9 E8 12 98 4E FF 48 8B 50 20 48 8B 82 50 91 00 00 48 85 C0 74 09
DESC: What it is: A hook that runs when the Crystalline Conflict record screen is starting to open. When it runs: It runs during the opening transition before the record screen is fully visible. Why you would care: Use it if you want an early hook before the history UI finishes appearing.
----------------------------------------
NAME: MKSRecord_HandleBackButtonInput_Deep
SIG:  48 89 5C 24 10 48 89 6C 24 18 56 48 83 EC 50 33 F6 4C 8D 99 D8 02 00 00 45 33 D2 48 8B E9
DESC: What it is: The back-button handler for the Crystalline Conflict record screen. When it runs: It runs when the player uses the back action to leave or step out of the record UI. Why you would care: Use it if you want a narrow hook for record-screen back or close input.
----------------------------------------
NAME: AgentColosseumRecord_ReceiveEvent_Deep
SIG:  4C 8B DC 49 89 5B 20 41 54 41 56 41 57 48 81 EC D0 00 00 00 48 8B 84 24 10 01 00 00 49 8B D8 4C 8B FA 4C 8B F1
DESC: What it is: The agent-side input handler for the Colosseum record or history flow. When it runs: It runs when the game routes record-screen input through the agent layer before the addon handles it. Why you would care: Use it if you want an earlier controller-layer hook for that record flow.
----------------------------------------
NAME: AgentColosseumRecord_Update_Deep
SIG:  40 53 48 83 EC 20 48 8B 41 28 48 8B D9 48 85 C0 0F 84 66 01 00 00 80 B8 07 38 00 00 00
DESC: What it is: The repeating update function for the Colosseum record agent. When it runs: It runs while the Colosseum record flow is active to keep the controller-side state current. Why you would care: Use it if you want a live hook while that record flow is open.
----------------------------------------
NAME: AgentColosseumRecord_Hide_Deep
SIG:  48 89 5C 24 18 56 57 41 57 48 83 EC 20 48 89 6C 24 40 45 33 FF 48 8B 69 28 48 8B F1 48 85 ED 74 76
DESC: What it is: The hide function for the Colosseum record agent. When it runs: It runs when the record flow is being closed and the active agent-side task state is being torn down. Why you would care: Use it if you want to detect when that record flow is being dismissed.
----------------------------------------
NAME: ColosseumRecord_OnRefresh_Deep
SIG:  48 89 6C 24 18 56 48 83 EC 20 F6 81 A1 01 00 00 01 49 8B F0 48 8B E9 75 0D 32 C0 48 8B 6C 24 40 48 83 C4 20 5E C3
DESC: What it is: The refresh function for the Colosseum record or history screen. When it runs: It runs when the game redraws the visible ranked-history data on that screen. Why you would care: Use it if you want a hook for changes to the displayed Colosseum history data.
----------------------------------------
NAME: ColosseumRecord_ReceiveEvent_Deep
SIG:  66 83 FA 19 0F 85 33 01 00 00 48 89 5C 24 08 57 48 83 EC 40 48 8B F9 41 8B D8 49 8B C9 33 D2 E8 1C E3 4B FF
DESC: What it is: The input handler for the Colosseum record or history screen. When it runs: It runs when the player interacts with that record screen. Why you would care: Use it if you want to track direct input on that history UI.
----------------------------------------
NAME: ColosseumRecord_HandleCustomInput_Deep
SIG:  40 53 48 83 EC 30 80 7A 04 00 48 8B D9 75 46 83 3A 02 75 41 48 8B 91 50 02 00 00 45 33 C9 41 B0 01
DESC: What it is: A helper that handles controller-style or custom input for the Colosseum record screen. When it runs: It runs when that screen receives alternate input paths that need special handling. Why you would care: Use it if you want to separate controller or custom input from ordinary click input.
----------------------------------------
NAME: ColosseumRecord_OnOpenTransitionStarted_Deep
SIG:  40 53 48 83 EC 20 48 8B D9 E8 12 18 4F FF 48 8B 50 20 48 8B 82 50 91 00 00 48 85 C0 74 09
DESC: What it is: A hook that runs when the Colosseum record screen is starting to open. When it runs: It runs during the opening transition before the history view is fully visible. Why you would care: Use it if you want an early hook before that record screen fully appears.
----------------------------------------
NAME: ColosseumRecord_HandleBackButtonInput_Deep
SIG:  48 89 5C 24 10 48 89 74 24 18 57 48 83 EC 50 80 B9 F8 02 00 00 00 41 0F B6 F8 48 8B F1 0F 84 36 01 00 00
DESC: What it is: The back-button handler for the Colosseum record screen. When it runs: It runs when the player uses the back action to leave that history UI. Why you would care: Use it if you want a narrow hook for back or close input on that screen.
----------------------------------------
NAME: PvpProfileColosseum_HandleCustomInput_Deep
SIG:  40 53 48 83 EC 30 83 3A 02 48 8B D9 75 5B 80 7A 04 00 75 55 E8 77 37 3F FF 0F B7 93 E8 01 00 00 48 8B 48 20
DESC: What it is: A helper that handles alternate input on the Colosseum page inside the PvP profile. When it runs: It runs when that profile page receives controller-style or other custom input. Why you would care: Use it if you want a focused hook for non-standard input on the Colosseum profile page.
----------------------------------------
NAME: PvpProfileColosseum_OnRequestedUpdate_Deep2
SIG:  40 53 48 83 EC 20 48 8B D9 E8 F2 0D 00 00 45 33 C9 41 B0 01 48 8B CB 41 8D 51 66 48 83 C4 20 5B E9 4B 24 3F FF
DESC: What it is: An alternate update-request path for the Colosseum page in the PvP profile. When it runs: It runs when the game wants to force a refresh of that page through the agent or controller layer. Why you would care: Use it if you want to catch forced profile-page refreshes before the visible redraw happens.
----------------------------------------
CATEGORY: PvP Map Objects and Pickups
----------------------------------------
NAME: EventFramework_InteractWithReactionEventObject_Deep
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B FA 48 8B D9 E8 3B 6D C4 00 4C 8D 83 80 3C 00 00 48 8B D7 48 8B C8
DESC: What it is: A shared world-interaction function used for reaction event objects such as pickups and other map objects you can interact with. When it runs: It runs when the player or game triggers an interaction with that kind of world object. Why you would care: Use it if you want a broad hook for interactions with pickup-style or map-interactable objects.
----------------------------------------
NAME: ReactionEventObject_Update_Deep
SIG:  40 53 48 83 EC 20 80 B9 B4 01 00 00 00 48 8B D9 74 4A 48 89 7C 24 30 48 8B B9 08 01 00 00 48 85 FF 74 34
DESC: What it is: The repeating update function for reaction event objects in the world. When it runs: It runs while those objects are active to keep their state, visuals, and timed behavior current. Why you would care: Use it if you want a live hook for world pickups or reaction-style map objects after they have spawned.
----------------------------------------
NAME: PacketDispatcher_HandleSpawnObjectPacket_Deep
SIG:  40 53 57 48 83 EC 58 F6 42 02 02 48 8B DA 40 0F 97 C7 83 3D 5F C3 DF 01 03 0F 84 75 03 00 00
DESC: What it is: The main network handler for object-spawn packets. When it runs: It runs when the client receives a packet telling it to create a new world object, including pickup-style or event objects. Why you would care: Use it if you want the earliest hook for new map objects entering the client from the network.
----------------------------------------
NAME: EventObjectManager_CreateEventObject_Deep
SIG:  48 89 5C 24 18 48 89 6C 24 20 57 41 54 41 57 48 83 EC 40 8B 9C 24 90 00 00 00 45 0F B7 F9 41 8B E8 44 8B E2 48 8B F9
DESC: What it is: The function that creates a normal EventObject in the game's event-object table. When it runs: It runs after object-spawn logic decides a new event object should be created. Why you would care: Use it if you want a hook close to the moment when a new event object, including some pickup-style objects, is created locally.
----------------------------------------
NAME: EventObject_InitFromDataRow_Deep
SIG:  48 89 5C 24 08 57 48 83 EC 20 0F B6 44 24 58 48 8B D9 88 81 B9 01 00 00 8B FA 0F B6 44 24 60 88 81 BA 01 00 00 66 C7 81 90 00 00 00 07 00 0F B6 81 91 00 00 00 66 44 89 81 B0 01 00 00 89 91 84 00 00 00
DESC: What it is: The setup function that fills in a type-7 EventObject from its data row and default state. When it runs: It runs while the game is turning an object id into a live event object with data, flags, and resources. Why you would care: Use it if you want one of the closest static hooks to the identity of pickup-style event objects.
----------------------------------------
NAME: EventObject_GetDataRow_Deep
SIG:  48 83 EC 28 48 8B 05 25 CB FE 01 44 8D 81 80 7B E1 FF BA 6A 00 00 00 48 8B 88 40 2B 00 00 E8 BD 7E DC FF 48 85 C0 75 05 48 83 C4 28 C3 48 8B 00
DESC: What it is: The helper that resolves the data row backing a live EventObject. When it runs: It runs when the game needs to turn an event object's id into its underlying data definition. Why you would care: Use it if you want the cleanest static link between a spawned event object and the data row that defines it.
----------------------------------------
NAME: EventFramework_CheckInteractRangeEx_Deep
SIG:  40 53 57 41 56 48 83 EC 70 48 8B 02 48 8B CA 41 0F B6 F9 4D 8B F0 48 8B DA FF 50 10 83 F8 01 74 19 48 8B 84 24 B0 00 00 00 C7 00 01 00 00 00 32 C0 48 83 C4 70 41 5E 5F 5B C3
DESC: What it is: The main extended interaction-range check used before the game allows interaction with certain world objects. When it runs: It runs when the game wants to decide whether a player is allowed to interact with a more complex object than the basic range check can handle. Why you would care: Use it if you want a hook for whether pickup-style or event-style objects are considered interactable.
----------------------------------------
NAME: EventObject_ApplyStateTransition_Deep
SIG:  40 53 55 56 57 41 56 48 81 EC 40 01 00 00 48 8B 05 13 C0 14 01 48 33 C4 48 89 84 24 30 01 00 00 0F B7 B1 B2 01 00 00
DESC: What it is: The function that applies a state change to a live EventObject. When it runs: It runs when the game updates the state of an event object, whether that change came from spawning, later object updates, or content-specific logic. Why you would care: Use it if you want a direct hook for live event-object state changes.
----------------------------------------
CATEGORY: Crystalline Conflict Labels
----------------------------------------
NAME: CrystallineConflict_FormatRecoveryFeatureLabel_Deep
SIG:  48 89 5C 24 10 48 89 6C 24 18 57 48 83 EC 20 48 8B 0D CA 9C E5 01 49 8B D8 48 8B EA E8 EF 1F 73 FF 48 8B F8 48 85 C0 75 1A 48 8B D5 48 8B CB 48 8B 5C 24 38 48 8B 6C 24 40 48 83 C4 20 5F
DESC: What it is: A text-formatting helper that builds visible Crystalline Conflict feature labels such as Recovery and Maintenance. When it runs: It runs when the game wants to turn stored feature data into visible localized text. Why you would care: Use it if you want a UI-side clue for Crystalline Conflict mechanics such as healing-related features, even though it does not identify the pickup object by itself.
----------------------------------------
CATEGORY: Quest Gates - Core State
----------------------------------------
NAME: QuestManager_Instance
SIG:  48 8D 0D ?? ?? ?? ?? 0F B6 D8 E8 ?? ?? ?? ?? 44 0F B6 C0 8D 53 01 41 3B D0 72 07 BA B6 07 00 00
DESC: What it is: A signature used to resolve the game's main QuestManager singleton. When it runs: It is used when code needs the central quest manager that stores quest state. Why you would care: Use it if you need a base pointer for quest acceptance, completion, sequence, or related quest-state reads.
----------------------------------------
NAME: QuestManager_IsQuestComplete
SIG:  40 53 48 83 EC 20 8B D9 E8 73 32 AC 00 0F B7 D3 48 8B C8 48 83 C4 20 5B E9 D3 D1 CA 00
DESC: What it is: A quest-completion check that answers whether a given quest is finished. When it runs: It runs whenever the client needs a quick yes or no answer about quest completion. Why you would care: Use it if you want a direct hook for quest-finished checks without rebuilding the underlying quest-state logic.
----------------------------------------
NAME: QuestManager_IsQuestComplete1
SIG:  0F B7 C2 4C 8B C9 44 8B C0 49 C1 E8 03 49 81 F8 EF 02 00 00 72 03 32 C0 C3 24 07 BA 80 00 00 00
DESC: What it is: A lower-level quest-completion check that reads quest completion state directly from the QuestManager data. When it runs: It runs when code wants a direct answer from the quest-state storage instead of a higher-level wrapper. Why you would care: Use it if you want a closer-to-the-data hook for quest completion checks.
----------------------------------------
NAME: QuestManager_IsQuestAccepted
SIG:  45 33 C0 48 8D 41 18 66 39 10 74 10 49 FF C0 48 83 C0 18 49 83 F8 1E 7C EE 32 C0 C3 B0 01 C3
DESC: What it is: The main check that answers whether a quest is currently accepted. When it runs: It runs when the client scans the active quest slots to see whether a specific quest is already in progress. Why you would care: Use it if you want a direct acceptance gate for quest-related plugin logic.
----------------------------------------
NAME: QuestManager_GetQuestSequence
SIG:  40 53 48 83 EC 20 0F B7 D9 E8 32 5D E1 FF 45 33 C0 41 8B D0 48 83 C0 10 66 39 58 08 74 18 41 FF
DESC: What it is: The function that returns the current sequence value for a quest. When it runs: It runs whenever the client needs the current quest step or progression stage. Why you would care: Use it if you want a direct read of quest progression state, which often controls NPCs, objects, and event flow.
----------------------------------------
NAME: QuestManager_GetQuestClassJob
SIG:  40 53 48 83 EC 20 0F B7 D9 E8 32 5C E1 FF 45 33 C0 41 8B D0 48 83 C0 10 66 39 58 08 74 18 41 FF
DESC: What it is: The function that returns the class or job requirement linked to a quest. When it runs: It runs when the client needs to know whether a quest is tied to a specific class or job. Why you would care: Use it if you want a direct hook for class-job quest gating.
----------------------------------------
NAME: QuestManager_IsMapMarkerUnlocked
SIG:  40 53 48 83 EC 20 0F B7 DA 66 85 DB 74 30 E8 3D 60 E1 FF 44 8B C3 49 C1 E8 03 49 83 F8 40 73 1E
DESC: What it is: The check that answers whether a quest-related map marker is unlocked for the local player. When it runs: It runs when the client needs to know whether a quest marker should be available on the map. Why you would care: Use it if you want a direct gate for quest-driven map-marker visibility.
----------------------------------------
CATEGORY: Quest Gates - Event Framework
----------------------------------------
NAME: EventFramework_InteractWithObject
SIG:  40 55 56 57 41 55 48 81 EC 88 01 00 00 48 8B 05 14 66 B5 01 48 33 C4 48 89 84 24 60 01 00 00 48
DESC: What it is: The high-level EventFramework function that starts interaction with a world object such as a quest NPC or quest object. When it runs: It runs when the game begins a standard scripted interaction with an object. Why you would care: Use it if you want a broad hook for quest-related object interactions before they branch into more specific systems.
----------------------------------------
NAME: EventFramework_CheckInteractRange
SIG:  48 83 EC 48 0F B6 44 24 70 88 44 24 28 48 8D 44 24 30 48 89 44 24 20 E8 74 34 00 00 48 83 C4 48
DESC: What it is: The main distance check used before the game allows interaction with an event-driven object. When it runs: It runs before a quest or event interaction is allowed to proceed. Why you would care: Use it if you want a simple hook for whether the player is close enough to interact.
----------------------------------------
NAME: EventFramework_CheckInteractRangeEx
SIG:  40 53 57 41 56 48 83 EC 70 48 8B 02 48 8B CA 41 0F B6 F9 4D 8B F0 48 8B DA FF 50 10 83 F8 01 74
DESC: What it is: An extended interaction-range check that adds extra object-aware rules on top of the basic distance test. When it runs: It runs when the game needs more than a simple range check before allowing interaction. Why you would care: Use it if you want a deeper hook for whether a quest object is actually interactable.
----------------------------------------
NAME: EventFramework_IsDailyQuestAvailable
SIG:  48 83 EC 38 48 81 C1 D8 42 00 00 C7 44 24 20 FF FF FF FF E8 48 2C 11 00 48 85 C0 0F 95 C0 48 83
DESC: What it is: A daily-quest availability check used by the EventFramework. When it runs: It runs before the game offers certain repeatable or daily quest content. Why you would care: Use it if you want a direct gate for daily-quest availability.
----------------------------------------
NAME: EventFramework_GetEventMapMarkers
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 48 83 EC 20 49 8B F0 0F B7 EA 48 8B F9 E8 CE 66
DESC: What it is: A helper that gathers quest and event map markers for the UI and event systems. When it runs: It runs when the game needs to build or refresh visible objective markers. Why you would care: Use it if you want a broad hook for quest marker generation.
----------------------------------------
NAME: EventFramework_GetQuestBattleDirector
SIG:  48 8B 81 00 01 00 00 4C 8B 81 08 01 00 00 49 3B C0 74 2C 41 B9 06 80 00 00 0F 1F 80 00 00 00 00
DESC: What it is: The lookup that returns the active quest-battle controller for scripted or instanced quest combat. When it runs: It runs when the client needs the current quest-battle director. Why you would care: Use it if you want a direct path to quest-combat state instead of inferring it from UI changes.
----------------------------------------
NAME: TargetSystem_InteractWithObject
SIG:  48 89 5C 24 10 48 89 6C 24 18 56 48 83 EC 20 48 8B E9 41 0F B6 F0 48 8B CA 48 8B DA E8 0F 54 4D
DESC: What it is: A lower-level target-system function that drives object interaction through the normal targeting path. When it runs: It runs when interaction starts from the standard target system instead of directly from higher-level event code. Why you would care: Use it if you want a lower-level hook for targeted quest-object interaction.
----------------------------------------
CATEGORY: Quest Gates - Availability
----------------------------------------
NAME: DailyQuestMap_GetQuestIfAvailable
SIG:  40 56 57 41 56 48 81 EC 80 00 00 00 48 8B 05 D5 40 A3 01 48 33 C4 48 89 44 24 68 48 8B 31 49 8B
DESC: What it is: A helper that filters a daily-quest candidate down to one that is actually available to the player. When it runs: It runs while the game is deciding whether a specific daily quest can be offered. Why you would care: Use it if you want a focused hook for single daily-quest availability checks.
----------------------------------------
NAME: DailyQuestMap_CalculateAvailableQuests
SIG:  48 89 5C 24 08 44 88 4C 24 20 55 56 57 41 54 41 55 41 56 41 57 48 8B EC 48 83 EC 50 49 8B 58 30
DESC: What it is: The main function that builds the current list of quests the player is allowed to pick up. When it runs: It runs when the game recalculates quest availability for display or interaction. Why you would care: Use it if you want a broad hook for quest-offer eligibility.
----------------------------------------
NAME: QuestEventHandler_OnQuestRowRead
SIG:  40 55 56 48 81 EC B8 00 00 00 48 8B 05 87 C2 A3 01 48 33 C4 48 89 84 24 A0 00 00 00 48 83 3D BC
DESC: What it is: The function that reads quest-row data into the quest event handler's internal state. When it runs: It runs when the game loads or applies quest-sheet data before later quest checks happen. Why you would care: Use it if you want a hook near the point where quest data becomes usable for later gating.
----------------------------------------
NAME: UI_UpdateQuestCompletion
SIG:  40 53 48 83 EC 20 48 8B D9 E8 F2 7D C6 00 48 85 C0 74 23 C6 43 28 00 8B 08 85 C9 74 15 E8 4E 46
DESC: What it is: A UI-side update function that refreshes quest completion state after progress changes. When it runs: It runs when the game wants the UI layer to reflect a new completion state. Why you would care: Use it if you want a hook for when quest completion starts affecting what the player sees.
----------------------------------------
NAME: UI_UpdateQuestToDo
SIG:  40 55 53 56 57 41 54 41 55 41 56 48 8D 6C 24 A0 48 81 EC 60 01 00 00 48 8B 05 FA 7D 86 01 48 33
DESC: What it is: The function that rebuilds the quest todo list shown to the player. When it runs: It runs when quest state changes and the visible objective list needs to be refreshed. Why you would care: Use it if you want a hook for changes to the player's visible quest objectives.
----------------------------------------
NAME: QuestUI_PlayQuestGimmickReaction
SIG:  48 89 6C 24 10 48 89 74 24 18 57 41 56 41 57 48 83 EC 50 48 8D 4C 24 20 E8 93 74 EE FE BA 01 00
DESC: What it is: A quest-UI helper that plays the visible scripted reaction tied to a quest object or event target. When it runs: It runs when a quest-driven object changes state and the game wants to show its reaction. Why you would care: Use it if you want a hook for those visible quest-object reactions.
----------------------------------------
NAME: QuestUI_EquipQuestModel
SIG:  48 89 5C 24 10 48 89 6C 24 18 48 89 74 24 20 41 56 48 83 EC 50 48 8B F1 48 8D 4C 24 20 E8 BE 1F
DESC: What it is: A quest-UI helper that equips quest-specific presentation models for scripted scenes or interactions. When it runs: It runs when the game needs to show a special quest model during an event. Why you would care: Use it if you want a hook for quest-specific model presentation.
----------------------------------------
CATEGORY: Quest Gates - Packet Feeds and Flags
----------------------------------------
NAME: PacketDispatcher_HandleCompletedQuestsPacket
SIG:  48 83 EC 28 4C 8B C1 48 81 FA EF 02 00 00 0F 85 1D 01 00 00 48 8D 05 B5 EB E3 01 B9 05 00 00 00
DESC: What it is: The network handler that imports the completed-quest bitset into local quest state. When it runs: It runs when the server sends the bulk completed-quest data to the client. Why you would care: Use it if you want a direct hook for when quest completion state is hydrated from the network.
----------------------------------------
NAME: PacketDispatcher_HandleUnlockedMapMarkersPacket
SIG:  48 83 EC 28 48 83 FA 40 75 57 0F 10 01 0F 11 05 6B ED E3 01 0F 10 49 10 0F 11 0D 70 ED E3 01 0F
DESC: What it is: The network handler that updates unlocked quest and event map markers. When it runs: It runs when the server sends map-marker unlock state to the client. Why you would care: Use it if you want a direct hook for quest-marker unlock updates.
----------------------------------------
NAME: PacketDispatcher_HandleQuestCompletePacket
SIG:  48 89 5C 24 10 48 89 6C 24 18 48 89 74 24 20 57 41 56 41 57 48 83 EC 20 0F B7 E9 49 8B F1 8B DD
DESC: What it is: The network handler for live quest-completion updates. When it runs: It runs when the server sends an incremental change to quest completion state instead of a full bulk refresh. Why you would care: Use it if you want a hook for live quest completion as it happens.
----------------------------------------
NAME: PacketDispatcher_HandleCompletedLegacyQuestsPacket
SIG:  48 83 EC 28 48 83 FA 28 0F 85 25 01 00 00 80 3D 59 F6 E3 01 00 0F 10 01 0F 11 05 8D EC E3 01 0F
DESC: What it is: The network handler that imports completion flags for older legacy quest content. When it runs: It runs when the server sends legacy quest completion data to the client. Why you would care: Use it if you need to track older quest completion state separately from the normal quest set.
----------------------------------------
NAME: PacketDispatcher_HandleQuestRepeatFlagsPacket
SIG:  48 83 FA 02 75 45 53 48 83 EC 20 80 3D 56 F4 E3 01 00 41 0F B6 D8 0F B7 01 66 89 05 AF E9 E3 01
DESC: What it is: The network handler that updates quest repeatability flags. When it runs: It runs when the server sends state that controls whether repeatable or daily quests are available again. Why you would care: Use it if you want a direct hook for repeatable-quest availability changes.
----------------------------------------
NAME: QuestManager_MapMarkersReceivedFlag
SIG:  0F 82 82 FE FF FF 44 38 2D 37 FC E3 01 75 14 C6 05 2E FC E3 01 01 E8 CD
DESC: What it is: A byte-pattern that catches the code path which marks quest map-marker data as received. When it runs: It runs right after the client applies the server-fed map-marker state. Why you would care: Use it if you want a hook for when quest map-marker data becomes available locally.
----------------------------------------
NAME: QuestManager_CompletedQuestsReceivedFlag
SIG:  48 6C 66 89 48 6C 41 0F B6 48 6E 88 48 6E 75 38 C6 05 AE F8 E3 01 01 E8
DESC: What it is: A byte-pattern that catches the code path which marks the completed quest bitset as received. When it runs: It runs after the client has accepted the bulk completed-quest state from the server. Why you would care: Use it if you want a small hook for the moment completed-quest data becomes ready.
----------------------------------------
NAME: QuestManager_CompletedLegacyQuestsReceivedFlag
SIG:  48 8D 0D 87 E5 E3 01 48 89 74 24 38 BA F8 00 00 00 48 89 7C 24 20 C6 05
DESC: What it is: A byte-pattern that catches the code path which marks legacy completed-quest state as received. When it runs: It runs after the client has accepted the legacy completion data from the server. Why you would care: Use it if you want a small hook for when older quest-completion data becomes ready.
----------------------------------------
NAME: QuestManager_DailyQuestsReceivedFlag
SIG:  E9 01 75 E4 44 38 0D EC F4 E3 01 75 14 C6 05 E3 F4 E3 01 01 E8 7F 73 0D
DESC: What it is: A byte-pattern that catches the code path which marks daily-quest state as loaded from the server. When it runs: It runs after the client accepts the daily-quest state from network data. Why you would care: Use it if you want a hook for when daily-quest state becomes available for local checks.
----------------------------------------
NAME: QuestManager_QuestRepeatFlagsReceivedFlag
SIG:  41 0F B6 D8 0F B7 01 66 89 05 AF E9 E3 01 75 14 C6 05 3F F4 E3 01 01 E8
DESC: What it is: A byte-pattern that catches the code path which marks quest repeatability flags as ready. When it runs: It runs after the client has applied repeatability data from the network. Why you would care: Use it if you want a hook for when repeatability gating becomes valid locally.
----------------------------------------
NAME: QuestManager_LeveQuestsReceivedFlag
SIG:  0F 82 43 FF FF FF 80 3D 95 F2 E3 01 00 75 14 C6 05 8C F2 E3 01 01 E8 1E
DESC: What it is: A byte-pattern that catches the code path which marks levequest acceptance data as received. When it runs: It runs after the client has accepted levequest state from the server. Why you would care: Use it if you want a small hook for when levequest data becomes usable locally.
----------------------------------------
NAME: QuestManager_CompletedLeveQuestsReceivedFlag
SIG:  0F B7 41 60 66 89 42 60 75 18 C6 05 33 F0 E3 01 01 E8 C4 6E 0D 00 48 8B
DESC: What it is: A byte-pattern that catches the code path which marks completed levequest state as received. When it runs: It runs after the client has accepted completed levequest data from the server. Why you would care: Use it if you want a small hook for when completed levequest state becomes available locally.
----------------------------------------
CATEGORY: Quest Gates - Journal and Accept UI
----------------------------------------
NAME: Journal_AbandonQuest
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 30 41 8B F8 8B DA 48 8B F1 E8 64 1C 16 00 48 8B C8 E8
DESC: What it is: The journal-side function used when the player abandons an accepted quest. When it runs: It runs when the game processes a quest abandon action from the journal. Why you would care: Use it if you want a direct hook for quest abandonment.
----------------------------------------
NAME: Journal_IsQuestAccepted
SIG:  40 53 48 83 EC 20 0F B7 DA 66 85 D2 74 2A E8 6D A2 08 00 32 C9 66 66 66 0F 1F 84 00 00 00 00 00
DESC: What it is: The journal-specific check that answers whether a quest is currently accepted. When it runs: It runs when the journal UI decides which actions or controls should be shown for a quest. Why you would care: Use it if you want a UI-facing acceptance gate from the journal side.
----------------------------------------
NAME: AgentQuest_Journal_OpenForQuest
SIG:  40 53 41 55 41 56 41 57 48 81 EC 28 02 00 00 48 8B 05 42 6F C2 01 48 33 C4 48 89 84 24 00 02 00
DESC: What it is: The main agent entrypoint for opening the quest journal directly to one specific quest. When it runs: It runs when the game opens the journal focused on a selected quest. Why you would care: Use it if you want a direct hook for journal-open actions tied to a specific quest.
----------------------------------------
NAME: QuestUI_QuestTodoList_vf1
SIG:  40 53 55 56 57 41 56 41 57 48 81 EC 58 01 00 00 48 8B 05 41 2F CB 01 48 33 C4 48 89 84 24 40 01
DESC: What it is: A main QuestTodoList callback entrypoint used by the quest objective UI. When it runs: It runs when the quest todo UI routes a callback through the QuestTodoList object. Why you would care: Use it if you want a deeper hook into quest-objective UI behavior than the outer update helpers.
----------------------------------------
NAME: QuestRecompleteManager_IsQuestRecompleteComplete
SIG:  40 53 48 83 EC 20 33 C0 48 8B D9 66 3B C2 74 40 0F B7 CA 0F BA E9 10 E8 64 7A F5 FE 48 85 C0 74
DESC: What it is: The check used by QuestRecompleteManager to decide whether a replay-style quest is complete. When it runs: It runs when the game needs a yes or no answer about replay-quest completion state. Why you would care: Use it if you want a direct completion gate for quest replay systems.
----------------------------------------
CATEGORY: Quest Gates - Deep UI and Directors
----------------------------------------
NAME: QuestBattleDirector_IsUnlocked
SIG:  48 83 EC 28 48 8B 02 48 8B CA FF 50 10 83 F8 02 0F 95 C0 48 83 C4 28 C3
DESC: Low-level quest-battle gate that reports whether the current quest-battle director considers itself unlocked and active.
----------------------------------------
NAME: QuestBattleDirector_SetSequence
SIG:  40 53 56 57 48 81 EC B0 00 00 00 48 8B 05 C6 12 A3 01 48 33 C4 48 89 84 24 A0 00 00 00 41 0F B6
DESC: Internal quest-battle sequence mutator used when scripted quest combat advances to a new stage.
----------------------------------------
NAME: QuestBattleDirector_Update
SIG:  40 53 48 83 EC 20 48 8B D9 E8 C2 60 EB FF 84 C0 0F 85 8D 00 00 00 38 83 70 04 00 00 0F 84 81 00
DESC: Main quest-battle director update loop that evaluates state transitions during scripted quest encounters.
----------------------------------------
NAME: QuestBattleDirector_Update2
SIG:  48 89 5C 24 10 48 89 74 24 18 55 57 41 56 48 8B EC 48 81 EC 80 00 00 00 48 8B 05 C9 17 A3 01 48
DESC: Secondary quest-battle update routine used by the director when handling more complex scripted progression.
----------------------------------------
NAME: QuestRedoMapMarkerManager_Initialize
SIG:  48 83 EC 28 48 83 3D 4C 08 14 01 00 0F 85 D3 00 00 00 48 89 5C 24 30 45 33 C0 33 D2 48 89 7C 24
DESC: Initialization path that brings up the quest redo map-marker manager and its replay marker state.
----------------------------------------
NAME: AgentQuest_JournalAccept_ReceiveEvent
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 41 56 41 57 48 83 EC 40 48 8B BC 24 80 00 00 00 40 32 F6 45 8B F9 49 8B E8 4C 8B F2 48 8B D9 48 83 FF 02 75 2D 48 8B 49 10 48 8B 01 FF 90 88 00 00 00
DESC: Agent-side accept-quest event dispatcher that reacts to confirmation UI actions and button presses.
----------------------------------------
NAME: AgentQuest_JournalResult_ReceiveEvent
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 48 89 7C 24 20 41 54 41 56 41 57 48 83 EC 40 48 8B BC 24 80 00 00 00 40 32 F6 45 8B E1 49 8B E8 4C 8B FA 48 8B D9 48 83 FF 02 75 2D 48 8B 49 10 48 8B 01 FF 90 88 00 00 00
DESC: Agent-side result-window event dispatcher that handles reward confirmation and close actions.
----------------------------------------
NAME: AddonQuest_JournalAccept_ReceiveEvent
SIG:  48 89 5C 24 18 48 89 6C 24 20 56 48 83 EC 40 49 8B E9 48 8B F1 66 83 FA 0F 0F 84 1B 02 00 00 48
DESC: Addon-level event handler for the quest accept window, processing clicks and gamepad input.
----------------------------------------
NAME: AddonQuest_JournalResult_ReceiveEvent
SIG:  48 89 5C 24 18 48 89 74 24 20 55 57 41 57 48 8B EC 48 83 EC 50 4D 8B F9 48 8B F1 66 83 FA 19 0F
DESC: Addon-level event handler for the quest result window, including accept/close progression actions.
----------------------------------------
NAME: AgentQuest_QuestRedoHud_OnGameEvent
SIG:  83 FA 07 0F 85 AA 00 00 00 53 48 83 EC 20 48 8B D9 E8 0A CA 28 00 66 83 78 08 00 0F 84 8D 00 00
DESC: Quest redo HUD game-event hook that responds to relevant quest replay events rather than only UI input.
----------------------------------------
NAME: AddonQuest_QuestRedoHud_ReceiveEvent
SIG:  66 83 FA 19 75 1F 53 48 83 EC 20 41 8B D0 49 8B D9 E8 1A 33 36 FF 33 D2 48 8B CB E8 00 38 33 FF
DESC: Addon-level event handler for the quest redo HUD overlay.
----------------------------------------
CATEGORY: Quest Gates - Managers and Event Handlers
----------------------------------------
NAME: QuestRecompleteManager_Initialize
SIG:  48 83 EC 28 48 83 3D FC 36 14 01 00 0F 85 A3 00 00 00 48 89 6C 24 38 45 33 C0 33 D2 48 89 7C 24
DESC: Initialization path that allocates and wires up seasonal quest replay state.
----------------------------------------
NAME: QuestEffectManager_Initialize
SIG:  48 83 EC 28 48 83 3D 24 90 14 01 00 75 2F 45 33 C0 33 D2 B9 88 01 00 00 E8 C3 BA 7D FE 48 85 C0
DESC: Initialization path for QuestEffectManager and its quest-linked effect containers.
----------------------------------------
NAME: QuestRedoManager_Initialize
SIG:  48 83 EC 28 48 83 3D 14 CE B9 01 00 0F 85 34 01 00 00 48 89 5C 24 30 45 33 C0 33 D2 48 89 7C 24
DESC: Initialization path for the main New Game Plus quest redo manager.
----------------------------------------
NAME: QuestTodoList_CallbackSheetWaiter_vf0
SIG:  48 89 5C 24 08 57 48 83 EC 20 8B DA 48 8B F9 E8 BC 9A 43 01 F6 C3 01 74 0D BA 50 00 00 00 48 8B
DESC: Callback-sheet waiter entrypoint that feeds quest todo data into the QuestTodoList object.
----------------------------------------
NAME: QuestTodoList_ListenItemCallback_vf0
SIG:  40 53 48 83 EC 20 48 8D 05 BB 00 55 01 48 8B D9 48 89 01 F6 C2 01 74 0A BA 10 00 00 00 E8 56 1B
DESC: Listener callback used when quest todo items change and the todo list must react.
----------------------------------------
NAME: QuestTodoList_vf0
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8D 05 87 39 55 01 48 8B F9 48 89 01 8B DA 48 8D 05 88 F9 54 01
DESC: Primary virtual entrypoint on QuestTodoList itself, useful when tracing todo list object behavior.
----------------------------------------
NAME: QuestEventHandler_CancelInteraction
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 48 83 EC 20 48 8B D9 40 32 FF 48 8B 0D 4F D7 A6
DESC: Cancels an active quest interaction through the quest event handler.
----------------------------------------
NAME: QuestEventHandler_GetIconId
SIG:  48 83 EC 38 8B 44 24 60 C6 44 24 28 00 89 44 24 20 E8 7A 05 00 00 48 83 C4 38 C3
DESC: Resolves the icon id used by quest interactions and quest-driven objects.
----------------------------------------
NAME: QuestEventHandler_GetNameplateIconForObject
SIG:  48 89 5C 24 20 55 41 56 41 57 48 83 EC 30 48 8B 2D 1B 49 C1 01 4C 8B F2 4C 8B F9 48 85 ED 74 5D
DESC: Maps a quest object to the icon shown on its nameplate, tying object presentation to quest-gate state.
----------------------------------------
NAME: QuestEventHandler_GetTodoArgs
SIG:  40 53 55 57 41 55 41 56 48 81 EC A0 00 00 00 48 8B 05 02 F1 A3 01 48 33 C4 48 89 44 24 78 48 8B
DESC: Builds the argument payload used by quest todo entries and objective presentation.
----------------------------------------
NAME: QuestEventHandler_IsTodoChecked
SIG:  48 89 5C 24 10 48 89 6C 24 18 56 48 83 EC 30 41 0F B6 E8 48 8B DA 48 8B F1 E8 C2 4F ED FF 84 C0
DESC: Checks whether a quest todo entry is already satisfied or ticked off.
----------------------------------------
NAME: QuestEventHandler_Initialize
SIG:  48 89 5C 24 08 57 48 83 EC 40 48 8B D9 E8 DE 6A ED FF 0F B7 BB E0 02 00 00 E8 82 6C E1 FF 33 C9
DESC: Main quest event handler initialization path that prepares quest object and event state.
----------------------------------------
NAME: QuestEventHandler_IsUnlocked
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 30 F6 81 14 05 00 00 04 48 8B F2 48 8B D9 74 69 0F B7
DESC: Reports whether the quest event handler considers its associated quest interaction unlocked.
----------------------------------------
NAME: AgentQuest_QuestRedo_IsActivatable
SIG:  48 83 EC 28 E8 B7 E8 28 00 84 C0 74 33 E8 0E 51 52 FF 84 C0 75 2A 48 89 5C 24 20 BB AF 0E 00 00
DESC: Gate used by the quest redo agent to determine whether the replay UI can currently be activated.
----------------------------------------
NAME: AddonQuest_QuestRedo_HandleBackButtonInput
SIG:  40 53 48 83 EC 30 48 83 B9 98 03 00 00 00 48 8B D9 0F 84 90 00 00 00 48 83 B9 A0 03 00 00 00 0F
DESC: Back-button handling path inside the quest redo addon, useful for tracing replay UI navigation gates.
----------------------------------------
NAME: AddonQuest_QuestRedo_HandleDPadInput
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 41 54 41 55 41 56 41 57 48 83 EC 70 45 0F B6 F8
DESC: D-pad navigation handling path inside the quest redo addon.
----------------------------------------
CATEGORY: Quest Gates - Journal and Redo Flow
----------------------------------------
NAME: AgentQuest_Journal_IsActivatable
SIG:  40 53 48 83 EC 20 BA 04 00 00 00 48 8B D9 E8 FD B9 8B FF 48 85 C0 74 17 BA 04 00 00 00 48 8B C8
DESC: Gate used before the quest journal agent can be activated or shown to the player.
----------------------------------------
NAME: AgentQuest_Journal_ReceiveEvent
SIG:  4C 8B DC 55 53 41 54 41 56 41 57 49 8D 6B C8 48 81 EC 10 01 00 00 48 8B 05 7B 7C C2 01 48 33 C4
DESC: Main event dispatcher for the quest journal agent, handling UI-driven journal actions.
----------------------------------------
NAME: AddonQuest_JournalDetail_ReceiveEvent
SIG:  48 89 5C 24 10 48 89 74 24 18 4C 89 74 24 20 55 48 8B EC 48 83 EC 50 4D 8B F1 41 8B D8 48 8B F1
DESC: Event handler for the quest detail window, processing quest-detail interactions.
----------------------------------------
NAME: AgentQuest_QuestRedo_ReceiveEvent
SIG:  48 89 5C 24 10 57 48 83 EC 20 48 83 79 28 00 4D 8B D0 48 8B FA 48 8B D9 0F 84 C5 00 00 00 45 85
DESC: Main event dispatcher for the quest redo agent.
----------------------------------------
NAME: AddonQuest_QuestRedo_ReceiveEvent
SIG:  66 83 FA 19 0F 85 F0 03 00 00 56 41 57 48 83 EC 48 48 89 5C 24 60 4D 8B F9 41 0F B6 D0 48 8B F1
DESC: Addon-level event handler for the quest redo window.
----------------------------------------
NAME: AgentQuest_QuestRedoHud_ReceiveEvent
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B DA 48 8B F9 4D 85 C0 74 69 49 8B C8 E8 C3 A1 A5 FF 83 E8 0B
DESC: Event dispatcher for the quest redo HUD helper agent.
----------------------------------------
CATEGORY: Quest Gates - Named Surface and Deep Unknowns
----------------------------------------
NAME: AddonQuest_JournalDetail_HandleCustomInput
SIG:  40 53 48 83 EC 30 80 7A 04 00 48 8B D9 75 5B 83 3A 02 75 56 E8 D7 99 4F FF 0F B7 93 E8 01 00 00
DESC: Custom-input handler for the quest detail addon, useful for tracing non-default quest-detail controls.
----------------------------------------
NAME: QuestBattleDirector_vf2_Deep
SIG:  40 57 48 83 EC 20 48 8B F9 8B 0D 91 66 BF 01 E8 6C 66 A6 FF 48 85 C0 0F 84 B3 00 00 00 48 89 5C
DESC: Deep unnamed quest battle director method. Included because it is still part of the signable quest-battle control surface.
----------------------------------------
NAME: QuestBattleDirector_vf3_Deep
SIG:  40 53 48 83 EC 20 48 8B D9 E8 C2 62 EB FF 84 C0 74 1E 48 8B 8B 80 06 00 00 48 85 C9 74 12 48 8B
DESC: Deep unnamed quest battle director method. Likely participates in the battle-state dispatch chain.
----------------------------------------
NAME: QuestBattleDirector_vf4_Deep
SIG:  40 53 48 83 EC 20 48 8B D9 E8 E2 62 EB FF 84 C0 75 1E 48 8B 8B 80 06 00 00 48 85 C9 74 0A 48 8B
DESC: Deep unnamed quest battle director method adjacent to the main quest-battle update chain.
----------------------------------------
NAME: QuestBattleDirector_vf49_Deep
SIG:  40 53 48 83 EC 20 48 8B D9 E8 72 32 EC FF 84 C0 75 08 48 8B CB E8 26 EA FF FF B0 01 48 83 C4 20
DESC: Deep unnamed quest battle director method with quest-battle state dependencies.
----------------------------------------
NAME: QuestBattleDirector_vf62_Deep
SIG:  81 FA 01 00 00 10 0F 85 0A 01 00 00 48 81 EC 38 01 00 00 48 8B 05 9E 19 A3 01 48 33 C4 48 89 84
DESC: Deep unnamed quest battle director method that handles a larger quest-battle state payload.
----------------------------------------
NAME: QuestBattleDirector_vf276_Deep
SIG:  41 56 48 81 EC D0 00 00 00 48 8B 05 38 08 A3 01 48 33 C4 48 89 84 24 B0 00 00 00 4C 8B F1 84 D2
DESC: Deep unnamed quest battle director method later in the vtable, included for exhaustive signature coverage.
----------------------------------------
NAME: QuestEventHandler_IsOccupied33
SIG:  48 83 EC 38 8B 44 24 60 89 44 24 20 E8 7F 0F 01 00 83 F8 21 0F 94 C0 48 83 C4 38 C3
DESC: Named quest event-handler occupancy/state check used by the quest interaction pipeline.
----------------------------------------
NAME: QuestEventHandler_vf88_Deep
SIG:  4C 8B DC 55 57 41 56 41 57 49 8D AB A8 FE FF FF 48 81 EC 38 02 00 00 48 8B 05 1A 97 A4 01 48 33
DESC: High-signal unnamed QuestEventHandler vtable method with many xrefs. Included as a deep quest-event signature.
----------------------------------------
NAME: QuestEventHandler_vf211_Deep
SIG:  48 89 5C 24 10 57 48 83 EC 20 48 8B DA 48 8B F9 48 8B 15 C9 28 C1 01 48 85 D2 0F 84 B7 00 00 00
DESC: Deep unnamed QuestEventHandler method in the later vtable region, likely part of advanced event dispatch.
----------------------------------------
NAME: QuestEventHandler_vf252_Deep
SIG:  48 89 4C 24 08 53 55 57 41 55 41 56 48 83 EC 40 4C 8B AA 08 01 00 00 41 0F B7 E9 41 0F B7 D8 4C
DESC: Deep unnamed QuestEventHandler method that accepts a richer quest-event payload.
----------------------------------------
NAME: QuestEventHandler_vf271_Deep
SIG:  40 56 41 54 41 55 41 56 48 83 EC 38 4C 8B EA 4C 8B F1 E8 69 01 01 00 49 8B D5 49 8B CE 44 0F B6
DESC: Deep unnamed QuestEventHandler method near the late-stage vtable dispatch group.
----------------------------------------
NAME: QuestEventHandler_vf272_Deep
SIG:  41 55 41 56 41 57 48 83 EC 40 4C 8B FA 4C 8B F1 48 85 D2 0F 84 7C 02 00 00 4C 8B 2D F0 18 C1 01
DESC: Deep unnamed QuestEventHandler method adjacent to vf271, included for exhaustive quest-event coverage.
----------------------------------------
CATEGORY: Quest Gates - UI Lifecycle and Early Vtable
----------------------------------------
NAME: QuestTodoList_vf1
SIG:  40 53 55 56 57 41 56 41 57 48 81 EC 58 01 00 00 48 8B 05 41 2F CB 01 48 33 C4 48 89 84 24 40 01
DESC: Secondary virtual dispatch entry for QuestTodoList.
----------------------------------------
NAME: QuestEventHandler_vf2
SIG:  40 53 48 83 EC 20 48 8B 01 48 8B D9 FF 50 18 84 C0 75 67 48 8B 03 48 8B CB FF 50 20 84 C0 75 5A
DESC: Early quest-event virtual method in the core dispatch chain.
----------------------------------------
NAME: QuestEventHandler_vf5
SIG:  40 53 48 83 EC 20 48 8B D9 E8 E2 05 ED FF 84 C0 74 14 48 8B CB E8 A6 1B EE FF 84 C0 74 08 B0 01
DESC: Early quest-event virtual method tied to quest-state gating checks.
----------------------------------------
NAME: QuestEventHandler_vf8
SIG:  40 53 48 83 EC 30 48 8B D9 E8 02 07 ED FF F6 43 6C 02 74 22 BA 01 80 00 00 66 39 93 12 05 00 00
DESC: Early quest-event virtual method that inspects quest-event state flags.
----------------------------------------
NAME: QuestEventHandler_vf9
SIG:  48 89 5C 24 18 55 56 57 48 83 EC 40 48 8B 2D DD 7D C1 01 41 0F B7 F8 48 C7 44 24 78 00 00 00 00
DESC: Early quest-event virtual method with a wider quest-state payload.
----------------------------------------
NAME: QuestEventHandler_vf10
SIG:  40 53 48 83 EC 30 48 8B D9 E8 02 06 ED FF F6 43 6C 02 74 22 BA 01 80 00 00 66 39 93 12 05 00 00
DESC: Early quest-event virtual method adjacent to vf8 in the unlock and occupancy path.
----------------------------------------
NAME: QuestEventHandler_vf15
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 40 48 8B 3D 5A 7C C1 01 48 8B F2 48 8B D9 48 85 FF 74
DESC: Early quest-event virtual method that dispatches through quest-event globals.
----------------------------------------
NAME: QuestEventHandler_vf16
SIG:  40 53 48 83 EC 30 48 8B D9 E8 92 06 ED FF F6 43 6C 02 74 22 BA 01 80 00 00 66 39 93 12 05 00 00
DESC: Early quest-event virtual method in the same gating cluster as vf8 and vf10.
----------------------------------------
NAME: QuestEventHandler_vf17
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 20 57 48 83 EC 40 48 8B 3D 65 7B C1 01 48 8B F2 48 8B
DESC: Early quest-event virtual method with broader quest-event dispatch state.
----------------------------------------
NAME: QuestEventHandler_vf18
SIG:  40 53 48 83 EC 30 48 8B D9 E8 A2 05 ED FF F6 43 6C 02 74 22 BA 01 80 00 00 66 39 93 12 05 00 00
DESC: Early quest-event virtual method that checks the same quest-event state mask family.
----------------------------------------
NAME: QuestEventHandler_vf19
SIG:  48 89 5C 24 10 48 89 74 24 18 41 56 48 83 EC 40 4C 8B 35 F9 79 C1 01 0F B7 DA 48 8B F1 4D 85 F6
DESC: Early quest-event virtual method with a richer dispatch context and high xref count.
----------------------------------------
NAME: QuestEventHandler_vf20
SIG:  40 53 48 83 EC 30 48 8B D9 E8 02 05 ED FF 48 83 3D 2A 79 C1 01 00 74 28 F6 43 6C 02 74 22 BA 01
DESC: Early quest-event virtual method that branches through a quest-event global before checking state flags.
----------------------------------------
NAME: QuestEventHandler_vf21
SIG:  48 89 5C 24 10 48 89 6C 24 18 48 89 74 24 20 57 41 56 41 57 48 83 EC 40 F6 81 B0 05 00 00 04 45
DESC: Early quest-event virtual method in the broader event dispatch and gating surface.
----------------------------------------
CATEGORY: Quest Gates - Mid Vtable Dispatch
----------------------------------------
NAME: QuestEventHandler_vf22
SIG:  40 53 48 83 EC 30 48 8B D9 E8 C2 03 ED FF F6 43 6C 02 74 22 BA 01 80 00 00 66 39 93 12 05 00 00
DESC: Mid-stage quest-event virtual method in the same state-mask family as the other early unlock and occupancy checks.
----------------------------------------
NAME: QuestEventHandler_vf29
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 48 8B DA 48 8B F9 E8 F6 01 ED FF 48 8B 35 4F 73 C1
DESC: Mid-stage quest-event virtual method with a shared quest-event dependency chain.
----------------------------------------
NAME: QuestEventHandler_vf30
SIG:  48 89 5C 24 08 4C 89 4C 24 20 4C 89 44 24 18 48 89 54 24 10 55 56 57 41 54 41 55 41 56 41 57 48 83 EC 70 4C 8B 35 06 77 C1 01 4C 8B E9 0F 29 74 24 60 4D 85 F6 0F 84 09 03 00 00 F6 81 B0 05 00 00 04
DESC: Mid-stage quest-event virtual method with a wide argument payload and heavier dispatch logic.
----------------------------------------
NAME: QuestEventHandler_vf31
SIG:  40 53 48 83 EC 30 48 8B D9 E8 D2 02 ED FF F6 43 6C 02 74 22 BA 01 80 00 00 66 39 93 12 05 00 00
DESC: Mid-stage quest-event virtual method that reuses the common quest-event state-bit gate.
----------------------------------------
NAME: QuestEventHandler_vf35
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 48 83 EC 30 49 8B F1 41 0F B7 E8 48 8B DA 48 8B
DESC: Mid-stage quest-event virtual method with richer sequence and state inputs.
----------------------------------------
NAME: QuestEventHandler_vf41
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 48 83 EC 20 41 0F B6 D8 49 8B E9 48 8B FA 48 8B
DESC: Mid-stage quest-event virtual method that operates on byte-oriented quest-event state.
----------------------------------------
NAME: QuestEventHandler_vf42
SIG:  48 89 5C 24 20 55 56 57 41 54 41 55 41 56 41 57 48 8D AC 24 70 FF FF FF 48 81 EC 90 01 00 00 48 8B 05 32 AF A4 01 48 33 C4 48 89 85 80 00 00 00 33 C0 0F B6 F2 89 44 24 78 4C 8B F1 89 44 24 44 8B F8
DESC: Mid-stage quest-event virtual method with a large local frame and complex quest-event dispatch.
----------------------------------------
NAME: QuestEventHandler_vf47
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 48 83 EC 40 48 8B D9 49 8B F9 48 8D 0D 47 59 C4
DESC: Mid-stage quest-event virtual method tied to a shared global dispatch table.
----------------------------------------
NAME: QuestEventHandler_vf49
SIG:  40 55 41 57 48 8D 6C 24 B1 48 81 EC A8 00 00 00 48 8B 05 81 A5 A4 01 48 33 C4 48 89 45 07 4C 8B
DESC: High-signal quest-event virtual method in the mid vtable range.
----------------------------------------
NAME: QuestEventHandler_vf53
SIG:  40 53 48 83 EC 20 48 8B 01 48 8B D9 FF 90 80 07 00 00 48 8B 03 48 8B CB FF 90 90 06 00 00 48 8B 03 48 8B CB FF 90 00 07 00 00 48 8B 03 48 8B CB FF 90 C0 06 00 00 48 8B 03 48 8B CB FF 90 C8 06 00 00 B0 01 48 83 C4 20 5B C3 CC CC CC CC CC CC 40 53 48 83 EC 20 48 8B 01 48 8B D9 FF 90 80 07 00 00 48 8B 03 48 8B CB FF 90 90 06 00 00 48 8B 03 48 8B CB FF 90 00 07 00 00 48 8B 03 48 8B CB FF 90 C0 06 00 00 48 8B 03 48 8B CB FF 90 C8 06 00 00 B0 01 48 83 C4 20 5B C3 CC CC CC CC CC CC 40 55 57 41 57 48 83 EC 40 48 8B 3D 40 4D C1 01
DESC: Mid-stage quest-event virtual method that forwards through later vtable entries.
----------------------------------------
NAME: QuestEventHandler_vf54
SIG:  40 53 48 83 EC 20 48 8B 01 48 8B D9 FF 90 80 07 00 00 48 8B 03 48 8B CB FF 90 90 06 00 00 48 8B 03 48 8B CB FF 90 00 07 00 00 48 8B 03 48 8B CB FF 90 C0 06 00 00 48 8B 03 48 8B CB FF 90 C8 06 00 00 B0 01 48 83 C4 20 5B C3 CC CC CC CC CC CC 40 55 57 41 57 48 83 EC 40 48 8B 3D 40 4D C1 01 45 8B F9 48 8B E9 48 85 FF
DESC: Sister method to vf53 in the forward-dispatch quest-event chain.
----------------------------------------
NAME: QuestEventHandler_vf57
SIG:  40 53 48 83 EC 20 48 8B 59 70 48 85 DB 74 3D 41 83 F9 01 74 37 0F B6 83 90 00 00 00 3C 0E 77 2C
DESC: Mid-stage quest-event virtual method that branches on embedded quest-event mode values.
----------------------------------------
CATEGORY: Quest Gates - Late Vtable Dispatch
----------------------------------------
NAME: QuestEventHandler_vf58
SIG:  48 89 74 24 20 41 54 41 56 41 57 48 83 EC 20 48 8B F1 48 89 5C 24 40 48 8B 0D B2 CF A6 01 45 8B
DESC: Late-stage quest-event virtual method that reaches into shared quest-event globals and mode values.
----------------------------------------
NAME: QuestEventHandler_vf59
SIG:  40 55 53 56 48 8B EC 48 81 EC 80 00 00 00 48 8B 05 23 9D A4 01 48 33 C4 48 89 45 E0 48 83 B9 00
DESC: Late-stage quest-event virtual method with a larger local frame and higher-signal state handling.
----------------------------------------
NAME: QuestEventHandler_vf62
SIG:  40 55 57 41 57 48 83 EC 40 48 8B 3D 40 4D C1 01 45 8B F9 48 8B E9 48 85 FF 0F 84 13 01 00 00 48
DESC: Late-stage quest-event virtual method with a heavier dispatch path and global quest-event state access.
----------------------------------------
NAME: QuestEventHandler_vf63
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B DA 48 8B F9 E8 6B 1B EE FF 84 C0 74 48 48 8B 15 A0 7F C1 01
DESC: Late-stage quest-event virtual method adjacent to the early unlock/cancel path.
----------------------------------------
NAME: QuestEventHandler_vf69
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B DA 48 8B F9 E8 5B F1 EC FF 48 8B D3 48 8B CF 48 8B 5C 24 30
DESC: Late-stage quest-event virtual method that forwards through a separate quest-event processing helper.
----------------------------------------
NAME: QuestEventHandler_vf71
SIG:  48 89 5C 24 18 48 89 6C 24 20 41 56 48 83 EC 60 45 8B F0 48 8B DA 48 8B E9 E8 42 E6 ED FF 84 C0
DESC: Late-stage quest-event virtual method with a richer argument payload and quest-state result handling.
----------------------------------------
NAME: QuestEventHandler_vf72
SIG:  48 89 5C 24 10 48 89 7C 24 18 55 48 8B EC 48 83 EC 70 48 8B 05 6F 82 A4 01 48 33 C4 48 89 45 F0
DESC: Late-stage quest-event virtual method with a wide stack frame and more complex dispatch behavior.
----------------------------------------
NAME: QuestEventHandler_vf76
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 20 57 41 54 41 55 41 56 41 57 48 83 EC 40 48 8B BC 24
DESC: Late-stage quest-event virtual method with a wide multi-register payload.
----------------------------------------
NAME: QuestEventHandler_vf77
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B DA 48 8B F9 48 8B 15 69 25 C1 01 48 85 D2 74 27 80 BB 90 00
DESC: Late-stage quest-event virtual method that checks an embedded mode byte against shared quest-event globals.
----------------------------------------
NAME: QuestEventHandler_vf78
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B DA 48 8B F9 48 8B 15 09 25 C1 01 48 85 D2 74 27 80 BB 90 00
DESC: Late-stage quest-event virtual method adjacent to vf77 in the same mode-check cluster.
----------------------------------------
NAME: QuestEventHandler_vf79
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B DA 48 8B F9 48 8B 15 A9 24 C1 01 48 85 D2 74 27 80 BB 90 00
DESC: Late-stage quest-event virtual method that continues the same state-byte family as vf77 and vf78.
----------------------------------------
NAME: QuestEventHandler_vf82
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 30 48 83 3D 89 4B C1 01 00 48 8B F9 0F 84 C1 00 00 00
DESC: Late-stage quest-event virtual method that first checks a shared quest-event global before dispatching.
----------------------------------------
CATEGORY: Quest Gates - Deep High-Numbered Vtable
----------------------------------------
NAME: QuestEventHandler_vf205
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B FA 48 8B D9 E8 7B 8E E1 FF 0F B7 8B E0 02 00 00 45 33 C0 48
DESC: High-numbered quest-event virtual method that reads replay-style quest-event state fields.
----------------------------------------
NAME: QuestEventHandler_vf212
SIG:  48 89 5C 24 08 48 89 6C 24 10 56 57 41 54 41 56 41 57 48 83 EC 40 4C 8B F9 48 8B FA 48 8B CA E8
DESC: High-numbered quest-event virtual method with a broad multi-register payload.
----------------------------------------
NAME: QuestEventHandler_vf214
SIG:  48 8B C4 55 56 57 41 54 48 83 EC 48 48 8B 35 1D 37 C1 01 45 33 E4 48 8B FA 48 8B E9 48 85 F6 0F
DESC: High-numbered quest-event virtual method that depends on a shared quest-event global and wider stack frame.
----------------------------------------
NAME: QuestEventHandler_vf215
SIG:  40 53 48 83 EC 20 48 8B 01 48 8B D9 FF 50 18 84 C0 74 11 F6 83 B0 05 00 00 04 75 08 B0 01 48 83
DESC: High-numbered quest-event virtual method that branches through a quest-event flag byte after a nested dispatch.
----------------------------------------
NAME: QuestEventHandler_vf219
SIG:  40 53 55 41 56 48 83 EC 30 49 8B D8 4C 8B F2 48 8B E9 E8 B9 D5 ED FF 84 C0 0F 84 3F 01 00 00 48
DESC: High-numbered quest-event virtual method with a larger control-flow surface and strong xref count.
----------------------------------------
NAME: QuestEventHandler_vf220
SIG:  48 89 5C 24 10 55 56 57 41 54 41 56 48 83 EC 40 45 8B E0 48 8B DA 48 8B E9 E8 42 D4 ED FF 84 C0
DESC: High-numbered quest-event virtual method adjacent to vf219 with a similar multi-register dispatch path.
----------------------------------------
NAME: QuestEventHandler_vf222
SIG:  41 57 48 81 EC A0 02 00 00 48 8B 05 98 73 A4 01 48 33 C4 48 89 84 24 70 02 00 00 4C 8B F9 E8 8D
DESC: High-numbered quest-event virtual method with a very large local frame and deep quest-event state handling.
----------------------------------------
NAME: QuestEventHandler_vf223
SIG:  48 89 5C 24 08 57 48 83 EC 20 0F B7 99 E0 02 00 00 48 8B F9 E8 67 7D E1 FF 45 33 D2 45 8B C2 41
DESC: High-numbered quest-event virtual method that reads quest-event replay-style fields before dispatch.
----------------------------------------
NAME: QuestEventHandler_vf224
SIG:  40 56 41 56 48 81 EC 08 01 00 00 48 8B 05 96 70 A4 01 48 33 C4 48 89 84 24 E0 00 00 00 48 8B 35
DESC: High-numbered quest-event virtual method with a large frame and quest-event global dependency.
----------------------------------------
NAME: QuestEventHandler_vf225
SIG:  40 53 41 54 41 56 41 57 48 83 EC 38 4C 8B 3D DD 45 C1 01 4C 8B F2 4C 8B E1 4D 85 FF 0F 84 E0 00
DESC: High-numbered quest-event virtual method that reaches through a later shared quest-event table.
----------------------------------------
NAME: QuestEventHandler_vf227
SIG:  48 89 5C 24 18 55 41 56 41 57 48 83 EC 30 48 8B 2D 3B 3E C1 01 4C 8B F2 4C 8B F9 48 85 ED 0F 84
DESC: High-numbered quest-event virtual method in the late dispatch cluster with shared global state access.
----------------------------------------
NAME: QuestEventHandler_vf228
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 48 89 7C 24 20 41 56 48 83 EC 50 48 8B 3D 4F 3D C1
DESC: High-numbered quest-event virtual method adjacent to vf227 with a broader register set and stack frame.
----------------------------------------
CATEGORY: Quest Gates - Ultra Deep Tail
----------------------------------------
NAME: QuestEventHandler_vf229
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 48 8B 01 48 8B F1 FF 50 18 84 C0 0F 84 4A 01 00 00 F6 86 B0 05 00 00 04 0F 85 3D 01 00 00 0F B7 9E E0 02 00 00 E8 17 97 E1 FF 33 D2 8B CA 48 83 C0 10 66 39 58 08
DESC: Deep high-numbered quest-event virtual method that reads replay-state fields and then walks the active quest-event slots.
----------------------------------------
NAME: QuestEventHandler_vf235
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 30 0F B6 51 64 48 8B F9 48 8B 59 70 48 8B 35 AF 2C C1 01 83 EA 01 74 2F 83 FA 07 75 13 48 85 DB 74 0E 48 8B 03 48 8B CB FF 50 10 83 F8 02 74 78 48 8B CF 48 8B 5C 24 40
DESC: Deep quest-event virtual method that branches on embedded event-mode bytes and then dispatches through a quest-event object.
----------------------------------------
NAME: QuestEventHandler_vf237
SIG:  48 89 5C 24 10 48 89 6C 24 18 56 57 41 56 48 83 EC 30 0F B7 99 E0 02 00 00 41 0F B6 F1 49 8B E8 4C 8B F2 48 8B F9 E8 75 7B E1 FF 45 33 DB 45 33 D2 48 83 C0 10 66 39 58 08 74 12 41 FF C3 49 FF C2 48 83 C0 18
DESC: Deep quest-event virtual method with a richer payload and a loop across active quest-event entries.
----------------------------------------
NAME: QuestEventHandler_vf238
SIG:  48 89 6C 24 20 56 57 41 54 48 83 EC 50 48 8B F2 45 8B E1 B2 12 49 8B F8 48 8B E9 E8 E0 DF EC FF 84 C0 75 11 48 8B AC 24 88 00 00 00 48 83 C4 50 41 5C 5F 5E C3 48 8B 07 48 8B CF 48 89 5C 24 70 4C 89 74 24 78
DESC: Deep quest-event virtual method that swaps between a fast-fail path and a larger object-dispatch path.
----------------------------------------
NAME: QuestEventHandler_vf240
SIG:  40 53 48 83 EC 20 48 8B 01 48 8B D9 FF 50 18 84 C0 0F 84 9D 00 00 00 48 8B 15 82 29 C1 01 48 85 D2 0F 84 8D 00 00 00 48 8B CB E8 C1 D6 00 00 48 8B CB 84 C0 74 16 E8 25 C5 ED FF 84 C0 75 75 48 8B CB 48 83 C4 20
DESC: Deep quest-event virtual method that combines nested virtual dispatch with global quest-event state checks.
----------------------------------------
NAME: QuestEventHandler_vf241
SIG:  48 89 5C 24 18 48 89 6C 24 20 57 41 54 41 57 48 83 EC 30 48 8B FA 48 8B E9 E8 72 C2 ED FF 84 C0 0F 84 02 01 00 00 48 8B 1D A3 26 C1 01 48 85 DB 0F 84 F2 00 00 00 48 8B CB E8 62 52 ED FF 4C 8B E0 48 85 C0 0F 84
DESC: Deep quest-event virtual method with multiple global lookups before continuing into a larger quest-state chain.
----------------------------------------
NAME: QuestEventHandler_vf254
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 0F B7 99 E0 02 00 00 41 8B F8 48 8B F1 E8 DF E8 E0 FF 45 33 C9 41 8B D1 48 83 C0 10 0F 1F 44 00 00 66 39 58 08 74 35 41 FF C1 48 FF C2 48 83 C0 18 48 83 FA 1E 7C EA
DESC: Deep quest-event virtual method that iterates the active quest-event list and then inspects replay-style object state.
----------------------------------------
NAME: QuestEventHandler_vf276
SIG:  4C 8B DC 41 56 48 81 EC D0 00 00 00 48 8B 05 05 54 A4 01 48 33 C4 48 89 84 24 B0 00 00 00 80 A1 B0 05 00 00 FB 4C 8B F1 84 D2 0F 84 86 01 00 00 48 8B 81 50 02 00 00 49 89 73 F0 80 38 00 0F 85 4A 01 00 00 49 89
DESC: Very deep quest-event virtual method with a large frame and a full quest-event state payload.
----------------------------------------
NAME: QuestEventHandler_vf277
SIG:  48 83 EC 38 44 0F B6 D2 48 8B 15 E1 47 C1 01 48 85 D2 75 07 33 C0 48 83 C4 38 C3 8B 44 24 60 89 44 24 28 44 89 4C 24 20 45 8B C8 45 0F B6 C2 E8 3C 14 01 00 48 83 C4 38 C3 CC CC CC CC CC CC CC 48 89 5C 24 08
DESC: Very deep quest-event virtual method that pivots through a compact quest-state helper before falling through to the next handler.
----------------------------------------
NAME: QuestEventHandler_vf280
SIG:  40 53 57 41 56 41 57 48 83 EC 68 48 8B 05 D6 5B A4 01 48 33 C4 48 89 44 24 58 80 BC 24 C0 00 00 00 00 45 8B F9 4D 8B F0 48 8B DA 48 8B F9 0F 85 DD 00 00 00 48 89 74 24 60 0F B6 B4 24 B8 00 00 00 44 0F B6 C6
DESC: Very deep quest-event virtual method with a wide stack frame and byte-oriented quest-state branching.
----------------------------------------
NAME: QuestEventHandler_vf283
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 0F B7 99 E0 02 00 00 41 8B F8 48 8B F1 E8 DF E7 E0 FF 45 33 C9 41 8B D1 48 83 C0 10 0F 1F 44 00 00 66 39 58 08 74 35 41 FF C1 48 FF C2 48 83 C0 18 48 83 FA 1E 7C EA
DESC: Very deep quest-event virtual method adjacent to vf254 in the later replay-state dispatch region.
----------------------------------------

CATEGORY: Variant and Criterion Dungeons - Core Systems
----------------------------------------
NAME: VariantDungeon1_vf402
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 57 41 56 41 57 48 83 EC 20 4C 8B 52 08 48 8B DA 48 8B E9 49 BF C5 4E EC C4 4E EC C4 4E 48 8B 0A 49 8B C7 4C 2B D1 4D 8B F1 49 F7 EA 49 8B F8 BE FF FF FF FF 48 C1 FA 05 48 8B C2 48 C1 E8 3F 48 03 D0 0F 84 5C 01 00 00 48 8D 15 22 14 97 00 E8 9D CD 70 FE 3C 01 75 07 33 F6 E9 45 01 00 00
DESC: What it is: One of the main Variant Dungeon control functions. When it runs: While a Variant Dungeon is active and the game is updating dungeon progress in the background. Why you would care: Use it if you want a deep hook for route progress or internal dungeon state changes.
----------------------------------------
NAME: VariantDungeon1_vf9
SIG:  48 83 EC 28 81 BA 84 00 00 00 D0 B7 1E 00 75 0E 45 0F B7 C0 45 33 C9 33 D2 E8 92 65 2F FF 32 C0 48 83 C4 28 C3
DESC: What it is: An early Variant Dungeon check. When it runs: Before the game moves into the next route step or internal dungeon action. Why you would care: Use it if you want to see when the game allows or blocks early Variant Dungeon progression.
----------------------------------------
NAME: VariantDungeon1_vf311
SIG:  40 56 57 41 56 48 83 EC 20 41 0F B6 F1 49 8B F8 4C 8B F1 81 EA 2B 04 00 00 74 09 83 FA 01 0F 85 05 01 00 00 48 8B 01 BA 92 85 00 00
DESC: What it is: A Variant Dungeon progress handler. When it runs: When the game updates route-specific progress or related dungeon state in the background. Why you would care: Use it if you want to track route progress beyond the normal UI layer.
----------------------------------------
NAME: VariantDungeon1_vf319
SIG:  40 53 48 83 EC 20 48 8B D9 0F B7 89 BE 0D 00 00 E8 4B 07 E7 FE 48 85 C0 74 13 0F 10 00 0F 11 83 98 1F 00 00 8B 40 10 89 83 A8 1F 00 00
DESC: What it is: A function that stores a small piece of Variant Dungeon progress data. When it runs: When the game records a route change or another internal dungeon state update. Why you would care: Use it if you want to watch the exact moment progress is written into the active dungeon state.
----------------------------------------
NAME: VariantDungeon1_vf378
SIG:  40 53 56 57 48 83 EC 50 48 8B 05 39 D6 E2 00 48 33 C4 48 89 44 24 40 41 8B F1 41 8B F8 48 8B D9 81 EA 01 00 00 10 0F 84 70 01 00 00 83 EA 01 0F 84 85 00 00 00 83 EA 01 74 44 83 FA 01 0F 85 83 01 00 00
DESC: What it is: A larger Variant Dungeon route and event handler. When it runs: When the game processes bigger route changes or event-driven dungeon transitions. Why you would care: Use it if you want one broad hook that sees several important Variant Dungeon changes.
----------------------------------------
NAME: VariantDungeon3_vf30
SIG:  48 89 5C 24 10 56 48 83 EC 20 48 8B D9 48 8B F2 48 8B 0D 89 B0 E7 00 E8 B4 33 75 FE 48 85 C0 0F 84 C6 00 00 00 4C 8B 00 48 8B C8
DESC: What it is: A Variant Dungeon helper that passes route information into the main dungeon logic. When it runs: When route-specific state needs to be handed off to the wider dungeon system. Why you would care: Use it if you want to connect route behavior to the main content flow.
----------------------------------------
NAME: CriterionDungeon_vf319
SIG:  40 53 48 83 EC 30 48 8B D9 0F B7 89 BE 0D 00 00 E8 5B AF E9 FE 48 85 C0 74 0C 0F B6 40 11 88 83 08 20 00 00 EB 07 0F B6 83 08 20 00 00
DESC: What it is: A function that stores a small piece of Criterion Dungeon state. When it runs: When the game updates internal Criterion progress or a related dungeon state value. Why you would care: Use it if you want to track state changes during a Criterion run at a deeper level.
----------------------------------------
NAME: CriterionDungeon_vf331
SIG:  40 53 48 83 EC 20 F6 81 8D 1F 00 00 10 48 8B D9 75 3B 80 B9 09 20 00 00 01 75 32 8B 81 04 20 00 00 85 C0 78 1B 3B D0 77 17 45 33 C0
DESC: What it is: A Criterion Dungeon progression check. When it runs: Before the game continues into the next Criterion step or related action. Why you would care: Use it if you want a clean gate for allowed versus blocked progression.
----------------------------------------
NAME: CriterionDungeon_vf346
SIG:  48 89 74 24 10 57 48 83 EC 20 80 B9 09 20 00 00 01 8B F2 48 8B F9 75 50 48 89 5C 24 30 E8 5E 73 2F FF 8B D8 8B 87 00 20 00 00 3B D8
DESC: What it is: A Criterion Dungeon state handler. When it runs: When the game branches into different Criterion state paths. Why you would care: Use it if you want one hook that sees several state-driven Criterion behaviors.
----------------------------------------
NAME: CriterionDungeon_vf402
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 4C 8B 4A 08 48 8B FA 48 8B D9 48 B8 C5 4E EC C4 4E EC C4 4E 48 8B 0A 49 8B F0 4C 2B C9
DESC: What it is: One of the main Criterion Dungeon control functions. When it runs: While a Criterion Dungeon is active and the game is maintaining its live state. Why you would care: Use it if you want a deeper hook into the background logic that runs the dungeon.
----------------------------------------

CATEGORY: Variant and Criterion Dungeons - Modules and Persistence
----------------------------------------
NAME: VVDNotebookModule_WriteFile
SIG:  48 83 EC 38 4C 8B CA 48 C7 44 24 20 35 00 00 00 48 8D 51 48 41 B8 34 00 00 00 48 8D 05 C7 8E 87 01 48 8D 4C 24 58 48 89 44 24 58
DESC: What it is: The save function for Variant Dungeon notebook progress. When it runs: When the game writes notebook progress to local save data. Why you would care: Use it if you want to track or react to notebook progress being saved.
----------------------------------------
NAME: VVDNotebookModule_ReadFile
SIG:  48 89 5C 24 10 55 56 57 48 8B EC 48 83 EC 60 48 8B 05 92 DB FE 01 48 33 C4 48 89 45 F8 49 8B F8 41 0F B7 F1 41 B8 04 00 00 00
DESC: What it is: The load function for Variant Dungeon notebook progress. When it runs: When the game reads notebook progress from local save data. Why you would care: Use it if you want to know when saved notebook progress is restored into memory.
----------------------------------------
NAME: VVDActionModule_WriteFile
SIG:  48 83 EC 38 4C 8B CA 48 C7 44 24 20 03 00 00 00 48 8D 51 48 41 B8 02 00 00 00 48 8D 05 57 89 87 01 48 8D 4C 24 58 48 89 44 24 58
DESC: What it is: The save function for selected Variant actions. When it runs: When the game writes your current Variant action setup to local save data. Why you would care: Use it if you want to track or react to action setup changes being saved.
----------------------------------------
NAME: VVDActionModule_ReadFile
SIG:  48 89 5C 24 10 57 48 83 EC 30 66 C7 41 48 00 00 48 8D 79 48 49 8B D8 66 41 83 F9 64 72 45 84 D2 74 41 48 85 DB 74 3C 44 8B 44 24 60
DESC: What it is: The load function for selected Variant actions. When it runs: When the game restores your saved Variant action setup for the UI. Why you would care: Use it if you want to know when saved action choices are loaded back into the game.
----------------------------------------

CATEGORY: Variant and Criterion Dungeons - Agents and UI
----------------------------------------
NAME: AgentVVDFinder_Show
SIG:  40 53 48 83 EC 20 48 8B 01 48 8B D9 FF 50 30 48 8B 13 48 8B CB 84 C0 74 09 48 83 C4 20 5B 48 FF 62 28 FF 52 40 84 C0 74 15 45 33 C9
DESC: What it is: The function that opens the Variant and Criterion finder window. When it runs: When the player or game requests the finder to appear. Why you would care: Use it as a clean hook for the moment the finder becomes visible.
----------------------------------------
NAME: AgentVVDFinder_Hide
SIG:  40 53 48 83 EC 20 48 8B D9 E8 F2 8E A4 FF 48 8B CB E8 7A 87 A4 FF 48 8B 03 48 8B CB FF 50 30 84 C0 74 0E 48 8B 4B 28 48 83 C4 20 5B
DESC: What it is: The function that closes the Variant and Criterion finder window. When it runs: When the finder is dismissed or shut down. Why you would care: Use it if you want to know when the window leaves the screen or is being cleaned up.
----------------------------------------
NAME: AgentVVDFinder_Update
SIG:  41 56 48 83 EC 50 48 8B 01 4C 8B F1 FF 50 30 84 C0 0F 84 4C 02 00 00 48 89 5C 24 60 49 8B 5E 28 48 89 6C 24 68 48 89 74 24 70
DESC: What it is: The main live update function for the Variant and Criterion finder window. When it runs: Repeatedly while the finder stays open. Why you would care: Use it if you want to watch the window refresh its visible state over time.
----------------------------------------
NAME: AgentVVDFinder_ReceiveEvent
SIG:  48 89 6C 24 18 56 57 41 54 41 55 41 57 48 81 EC D0 00 00 00 48 8B 84 24 20 01 00 00 40 32 ED 49 8B F0 4C 8B EA 48 8B F9 48 85 C0 75 25
DESC: What it is: The main input handler for the Variant and Criterion finder window. When it runs: When the player clicks, selects, confirms, or otherwise interacts with the finder. Why you would care: Use it if you want to track what the player is doing inside that UI.
----------------------------------------
NAME: AgentVVDFinder_IsActivatable
SIG:  48 83 EC 28 E8 87 D8 6B FF 84 C0 74 1E 0F B7 0D F8 82 F7 01 E8 87 EC DE FF 48 85 C0 74 0D 80 78 76 1E 74 07 32 C0 48 83 C4 28 C3
DESC: What it is: A check for whether the Variant and Criterion finder can be opened. When it runs: Before the game allows the finder to activate. Why you would care: Use it if you want to know when the finder is available versus blocked.
----------------------------------------
NAME: AgentVVDFinder_OnLevelChange
SIG:  40 53 48 83 EC 20 48 8B 01 48 8B D9 FF 50 30 84 C0 74 17 48 8B 4B 28 E8 64 33 00 00 48 8B 4B 28 48 83 C4 20 5B E9 16 35 00 00
DESC: What it is: A level-change refresh function for the Variant and Criterion finder. When it runs: After your character level changes. Why you would care: Use it if you want to watch the finder respond to changing player requirements.
----------------------------------------
NAME: AgentVVDFinder_OnClassJobChange
SIG:  40 53 48 83 EC 20 48 8B 01 48 8B D9 FF 50 30 84 C0 74 17 48 8B 4B 28 E8 24 33 00 00 48 8B 4B 28 48 83 C4 20 5B E9 D6 34 00 00
DESC: What it is: A class/job-change refresh function for the Variant and Criterion finder. When it runs: After you change class or job. Why you would care: Use it if you want to watch job-based availability or display rules update.
----------------------------------------
NAME: AgentVVDNotebook_Show
SIG:  40 53 48 83 EC 20 48 8B 01 48 8B D9 FF 50 30 84 C0 75 1A 41 B9 FF FF FF FF 45 33 C0 48 8B CB 41 8D 51 02 48 83 C4 20 5B E9 B3 03 00 00
DESC: What it is: The function that opens the Variant Dungeon notebook window. When it runs: When the notebook is shown to the player. Why you would care: Use it as a clean hook for when the notebook first becomes visible.
----------------------------------------
NAME: AgentVVDNotebook_Hide
SIG:  48 89 5C 24 18 57 48 83 EC 20 48 8B 01 48 8B F9 FF 50 30 84 C0 74 20 48 8B 5F 28 48 8B 4B 08 48 8B 01 FF 90 F0 01 00 00 48 8B C8 48 8D
DESC: What it is: The function that closes the Variant Dungeon notebook window. When it runs: When the notebook is dismissed or shut down. Why you would care: Use it if you want to know when the notebook leaves the screen.
----------------------------------------
NAME: AgentVVDNotebook_Update
SIG:  40 56 48 83 EC 40 48 8B F1 E8 D2 78 A4 FF 84 C0 0F 85 C4 00 00 00 48 8B 06 48 8B CE FF 50 30 84 C0 0F 84 B3 00 00 00 48 8B 46 28
DESC: What it is: The main live update function for the Variant Dungeon notebook window. When it runs: Repeatedly while the notebook stays open. Why you would care: Use it if you want to follow live notebook state changes on screen.
----------------------------------------
NAME: AgentVVDNotebook_ReceiveEvent
SIG:  48 89 5C 24 10 48 89 6C 24 18 48 89 74 24 20 41 56 48 83 EC 20 48 8B 44 24 50 40 32 ED 49 8B D8 4C 8B F2 48 8B F1 48 85 C0 75 40
DESC: What it is: The main input handler for the Variant Dungeon notebook window. When it runs: When the player clicks or navigates inside the notebook. Why you would care: Use it if you want to track page changes, selections, or other notebook interaction.
----------------------------------------
NAME: AddonVVDAction_OnSetup
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 48 8B D9 49 8B F8 48 8B 89 38 02 00 00 8B F2 48 85 C9 74 16 E8 28 9E 08 00 48 8B 8B 38 02 00 00
DESC: What it is: The setup function for the Variant action window. When it runs: When the action-selection window first opens. Why you would care: Use it if you want a hook for the initial build of that UI.
----------------------------------------
NAME: AddonVVDAction_OnRefresh
SIG:  48 83 EC 28 48 8B 89 38 02 00 00 48 85 C9 74 05 E8 AB 61 08 00 B0 01 48 83 C4 28 C3
DESC: What it is: The refresh function for the Variant action window. When it runs: When the game redraws the window using the current saved actions. Why you would care: Use it if you want to track changes to the visible action list or selected actions.
----------------------------------------
NAME: AddonVVDAction_ReceiveEvent
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 60 44 0F B7 D2 49 8B F1 41 8B D8 48 8B F9 41 83 EA 06 74 5E 41 83 EA 01 74 2E 41 83 FA 12
DESC: What it is: The main input handler for the Variant action window. When it runs: When the player clicks or makes a selection inside the action UI. Why you would care: Use it if you want to track direct player interaction with Variant actions.
----------------------------------------
NAME: AddonVVDNotebook_Update
SIG:  40 53 48 83 EC 20 48 8B D9 E8 E2 26 24 FF 48 8B 83 38 02 00 00 48 85 C0 74 2C 48 8B 88 F8 02 00 00 48 85 C9 74 20 48 8B 90 08 03 00 00
DESC: What it is: The live update function for the Variant notebook window. When it runs: Repeatedly while the notebook stays open. Why you would care: Use it if you want to track visible notebook changes after player actions or route changes.
----------------------------------------
NAME: AddonVVDNotebook_OnSetup
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 40 48 8B D9 49 8B F8 48 8B 89 38 02 00 00 8B F2 48 85 C9 74 16 E8 98 9D 08 00 48 8B 8B 38 02 00 00
DESC: What it is: The setup function for the Variant notebook window. When it runs: When the notebook window is first built. Why you would care: Use it if you want to inspect or change the starting notebook state.
----------------------------------------
NAME: AddonVVDNotebook_OnRefresh
SIG:  48 83 EC 28 48 8B 89 38 02 00 00 48 85 C9 74 0B 80 79 08 00 74 05 E8 05 5F 08 00 B0 01 48 83 C4 28 C3
DESC: What it is: The refresh function for the Variant notebook window. When it runs: After route changes, page changes, or other notebook-related updates. Why you would care: Use it if you want to track redraws tied to route progress.
----------------------------------------
NAME: AddonVVDNotebook_ReceiveEvent
SIG:  48 89 5C 24 10 48 89 74 24 18 57 48 83 EC 40 44 0F B7 D2 49 8B F1 48 8B F9 41 83 EA 0F 0F 84 F8 00 00 00 41 83 EA 0A 74 47 41 83 EA 2F
DESC: What it is: The main input handler for the Variant notebook window. When it runs: When the player clicks, selects, or navigates inside the notebook UI. Why you would care: Use it if you want to understand or hook notebook interaction.
----------------------------------------
NAME: AddonVVDFinder_Update
SIG:  40 57 48 83 EC 20 48 8B F9 E8 72 1F 24 FF 48 83 BF 38 02 00 00 00 0F 84 EA 00 00 00 48 89 5C 24 30 48 8B CF 48 89 6C 24 38 E8 E2 25 24 FF
DESC: What it is: The live update function for the Variant and Criterion finder window. When it runs: Repeatedly while the finder stays open. Why you would care: Use it if you want a strong hook for ongoing finder state changes.
----------------------------------------
NAME: AddonVVDFinder_OnSetup
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 40 48 8B F1 49 8B D8 48 8B 89 38 02 00 00 8B FA E8 BD 08 00 00 48 8B 8E 38 02 00 00 4C 8B C3
DESC: What it is: The setup function for the Variant and Criterion finder window. When it runs: When the finder window is first built. Why you would care: Use it if you want to inspect or hook the window's initial state.
----------------------------------------
NAME: AddonVVDFinder_OnRefresh
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 48 8B F9 49 8B F0 48 8B 89 38 02 00 00 E8 1F 15 00 00 0F B6 D8 84 C0 74 1C 48 8D 4E 50
DESC: What it is: The refresh function for the Variant and Criterion finder window. When it runs: When the game rebuilds the finder using the current search or filter state. Why you would care: Use it if you want to watch the list or selection state get rebuilt.
----------------------------------------
NAME: AddonVVDFinder_HandleCustomInput
SIG:  40 57 48 83 EC 30 48 8B B9 38 02 00 00 48 85 FF 74 7E 83 3A 02 75 79 48 8B 0F 48 89 5C 24 40 E8 9C 23 24 FF 48 8B C8 E8 74 98 21 FF
DESC: What it is: A special input handler for the Variant and Criterion finder window. When it runs: When the player uses custom selection input inside the finder. Why you would care: Use it if you want to track selection behavior that does not go through the simplest click path.
----------------------------------------
NAME: AddonVVDFinder_ReceiveEvent
SIG:  40 53 55 56 57 48 81 EC 88 00 00 00 48 8B 05 75 52 3C 01 48 33 C4 48 89 44 24 70 48 8B B1 38 02 00 00 49 8B E9 48 8B 9C 24 D0 00 00 00
DESC: What it is: The main input handler for the Variant and Criterion finder window. When it runs: When the player clicks, confirms, or otherwise interacts with the finder. Why you would care: Use it if you want one of the clearest hooks for player interaction in that UI.
----------------------------------------
NAME: AddonVVDFinder_HandleDPadInput
SIG:  48 89 5C 24 08 48 89 6C 24 10 48 89 74 24 18 48 89 7C 24 20 41 56 48 83 EC 30 45 0F B6 F0 8B F2 48 8B D9 E8 48 1E 24 FF 48 8B C8
DESC: What it is: The controller-navigation handler for the Variant and Criterion finder window. When it runs: When the player uses directional or gamepad-style input. Why you would care: Use it if you care about controller navigation instead of only mouse input.
----------------------------------------
NAME: AddonVVDVoteRoute_OnSetup
SIG:  48 8B C4 48 89 68 18 56 57 41 56 48 83 EC 70 48 8B B9 38 02 00 00 49 8B E8 44 8B F2 48 8B F1 48 85 FF 0F 84 77 01 00 00 48 8B 4F 08
DESC: What it is: The setup function for the Variant Dungeon route voting window. When it runs: When the route voting UI is first built. Why you would care: Use it if you want a clean hook for when route voting appears.
----------------------------------------
NAME: AddonVVDVoteRoute_OnRefresh
SIG:  40 56 48 83 EC 20 48 8B F1 48 8B 89 38 02 00 00 48 85 C9 74 51 48 89 5C 24 30 48 89 7C 24 38 E8 0C 28 08 00 48 8B 06 48 8B CE
DESC: What it is: The refresh function for the Variant Dungeon route voting window. When it runs: After the available choices or vote state changes. Why you would care: Use it if you want to track updates to the visible voting state.
----------------------------------------
NAME: AddonVVDVoteRoute_ReceiveEvent
SIG:  48 83 EC 48 66 83 FA 12 0F 84 CC 00 00 00 66 83 FA 23 0F 85 BD 00 00 00 48 89 74 24 58 48 8B B1 38 02 00 00 48 85 F6 0F 84 A3 00 00 00
DESC: What it is: The main input handler for the Variant Dungeon route voting window. When it runs: When the player clicks, selects, or confirms a route vote. Why you would care: Use it if you want to watch route voting interaction directly.
----------------------------------------
NAME: AddonVVDVoteRoute_OnRequestedUpdate
SIG:  40 53 48 83 EC 20 48 8B 99 38 02 00 00 48 85 DB 0F 84 A4 00 00 00 48 8B 4B 08 48 89 6C 24 30 48 89 7C 24 40 48 8B BA F0 04 00 00
DESC: What it is: A requested-refresh function for the route voting window. When it runs: When another part of the game asks the route voting UI to update. Why you would care: Use it if you want to catch route vote updates triggered from elsewhere.
----------------------------------------

CATEGORY: Variant and Criterion Dungeons - Lifecycle and Support
----------------------------------------
NAME: VariantDungeon2_ctor
SIG:  40 53 48 83 EC 20 48 8B D9 E8 82 B0 02 00 48 8D 05 6B 14 99 00 48 89 03 48 8D 05 F9 20 99 00 48 89 83 60 04 00 00 48 8D 05 03 21 99 00 48 89 83 68 04 00 00
DESC: What it is: A constructor for one Variant Dungeon controller object. When it runs: When the game creates that dungeon controller during setup. Why you would care: Use it if you want to hook the moment this Variant controller is first created.
----------------------------------------
NAME: VariantDungeon1_ctor
SIG:  40 53 48 83 EC 20 48 8B D9 E8 E2 AC 02 00 48 8D 05 8B 1D 99 00 41 B0 01 48 89 03 B2 02 48 8D 05 14 2A 99 00 48 8B CB 48 89 83 60 04 00 00
DESC: What it is: A constructor for the main Variant Dungeon controller object. When it runs: During setup before the dungeon starts running. Why you would care: Use it if you want an early hook for Variant Dungeon startup.
----------------------------------------
NAME: VariantDungeon3_ctor
SIG:  40 53 48 83 EC 20 48 8B D9 E8 92 AB 02 00 48 8D 05 0B 29 99 00 41 B0 01 48 89 03 B2 17 48 8D 05 94 35 99 00 48 8B CB 48 89 83 60 04 00 00
DESC: What it is: A constructor for another Variant Dungeon controller object. When it runs: During setup for a different Variant content type. Why you would care: Use it if you want coverage across more than one Variant controller.
----------------------------------------
NAME: CriterionDungeon_ctor
SIG:  40 53 48 83 EC 20 48 8B D9 E8 52 CF F6 FF 48 8D 05 0B 33 99 00 48 89 03 48 8D 8B 98 1F 00 00 48 8D 05 92 3F 99 00 48 89 83 60 04 00 00
DESC: What it is: A constructor for the main Criterion Dungeon controller object. When it runs: During setup before Criterion content begins running. Why you would care: Use it if you want an early hook for Criterion startup.
----------------------------------------
NAME: VVDNotebookModule_ctor
SIG:  40 53 48 83 EC 20 48 89 51 10 48 8D 05 CF E2 8C 01 48 89 01 4C 8D 05 25 43 8D 01 33 C0 48 8B D9 48 89 41 08 48 89 41 18 89 41 20
DESC: What it is: A constructor for the Variant notebook save-data module. When it runs: When the game creates the notebook save-data module. Why you would care: Use it if you want to hook the notebook save system at its start.
----------------------------------------
NAME: VVDActionModule_ctor
SIG:  40 53 48 83 EC 20 48 89 51 10 48 8D 05 2F DD 8C 01 48 89 01 4C 8D 05 75 3D 8D 01 33 C0 C7 41 40 01 00 00 00 48 8B D9 48 89 41 08
DESC: What it is: A constructor for the Variant action save-data module. When it runs: When the game creates the module that stores Variant action settings. Why you would care: Use it if you want to hook the action save system from the start.
----------------------------------------
NAME: AgentVVDFinder_ctor
SIG:  40 53 48 83 EC 20 48 8B D9 E8 62 91 A4 FF 48 8D 05 83 A6 6A 01 48 C7 43 28 00 00 00 00 48 89 03 48 8B C3 48 83 C4 20 5B C3
DESC: What it is: A constructor for the Variant and Criterion finder agent. When it runs: Before the finder window can be used. Why you would care: Use it if you want to hook the finder system as early as possible.
----------------------------------------
NAME: AgentVVDFinder_Finalizer
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B 79 28 48 8D 05 53 A6 6A 01 48 89 01 48 8B D9 48 85 FF 74 3E 48 8D 8F 68 03 00 00 E8 84 D0 06 00
DESC: What it is: A cleanup function for the Variant and Criterion finder agent. When it runs: When the game is finished with that agent. Why you would care: Use it if you want to track or react to finder shutdown and cleanup.
----------------------------------------
NAME: AgentVVDFinder_vf14
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B 01 48 8B D9 FF 50 28 48 8B 7B 28 48 85 FF 74 3E 48 8D 8F 68 03 00 00 E8 38 C3 06 00 48 8D 8F 20 41 00 00
DESC: What it is: An extra helper function tied to the Variant and Criterion finder agent. When it runs: As part of the agent's internal control flow. Why you would care: Use it if you need another hook near finder control and cleanup behavior.
----------------------------------------
NAME: AgentVVDNotebook_ctor
SIG:  40 53 48 83 EC 20 48 8B D9 E8 B2 7B A4 FF 48 8D 05 53 91 6A 01 48 C7 43 28 00 00 00 00 48 89 03 48 8B C3 C7 43 30 FF FF FF FF
DESC: What it is: A constructor for the Variant notebook agent. When it runs: Before the notebook window can be opened. Why you would care: Use it if you want an early hook for notebook system startup.
----------------------------------------
NAME: AddonVVDAction_ctor
SIG:  40 53 48 83 EC 20 48 8B D9 E8 A2 F1 23 FF 80 8B A3 01 00 00 08 48 8D 05 E4 91 D6 00 80 8B A0 01 00 00 20 80 8B A5 01 00 00 02 48 89 03
DESC: What it is: A constructor for the Variant action window object. When it runs: Before the action window is set up and shown. Why you would care: Use it if you want an early hook for the Variant action UI.
----------------------------------------
NAME: AddonVVDAction_Initialize
SIG:  48 89 4C 24 08 53 57 41 55 48 83 EC 40 48 8B D9 E8 AB 29 24 FF E8 06 F9 C7 FE 4C 8B C0 45 33 C9 33 D2 B9 10 06 00 00 E8 84 E1 C7 FE
DESC: What it is: An initialize function for the Variant action window. When it runs: During the early setup phase before the window is ready to use. Why you would care: Use it if you want to inspect or change the UI before it becomes active.
----------------------------------------
NAME: AddonVVDAction_Finalizer
SIG:  48 89 6C 24 18 56 48 83 EC 20 48 8B A9 38 02 00 00 48 8B F1 48 85 ED 74 5A 48 89 5C 24 30 48 8D 9D 98 06 00 00 48 89 7C 24 38 BF 02 00 00 00
DESC: What it is: A cleanup function for the Variant action window. When it runs: When the game is finished with that window. Why you would care: Use it if you want to track or react to the action UI being cleaned up.
----------------------------------------
NAME: AddonVVDNotebook_ctor
SIG:  40 53 48 83 EC 20 48 8B D9 E8 02 ED 23 FF 80 8B A3 01 00 00 08 48 8D 05 94 8F D6 00 80 8B A0 01 00 00 20 80 8B A5 01 00 00 02 48 89 03
DESC: What it is: A constructor for the Variant notebook window object. When it runs: Before the notebook window is set up and shown. Why you would care: Use it if you want an early hook for the notebook UI.
----------------------------------------
NAME: AddonVVDNotebook_Initialize
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B F9 E8 0E 25 24 FF E8 69 F4 C7 FE 4C 8B C0 45 33 C9 33 D2 B9 88 03 00 00 E8 E7 DC C7 FE 33 C9 48 8B D8
DESC: What it is: An initialize function for the Variant notebook window. When it runs: During the early setup phase before the notebook is ready to use. Why you would care: Use it if you want to inspect or change notebook UI state before it becomes active.
----------------------------------------
NAME: AddonVVDNotebook_Finalizer
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B B9 38 02 00 00 48 8B D9 48 85 FF 74 24 48 8D 8F 20 03 00 00 E8 0B 79 C7 FE BA 88 03 00 00 48 8B CF
DESC: What it is: A cleanup function for the Variant notebook window. When it runs: When the game is finished with that window. Why you would care: Use it if you want to track or react to notebook UI cleanup.
----------------------------------------
NAME: AddonVVDFinder_ctor
SIG:  40 53 48 83 EC 20 48 8B D9 E8 22 E6 23 FF 80 8B A3 01 00 00 08 48 8D 05 04 8B D6 00 80 8B A0 01 00 00 20 80 8B A5 01 00 00 02 81 8B C8 01 00 00 00 01 00 00
DESC: What it is: A constructor for the Variant and Criterion finder window object. When it runs: Before the finder window is set up and shown. Why you would care: Use it if you want an early hook for finder UI creation.
----------------------------------------
NAME: AddonVVDFinder_Initialize
SIG:  48 89 5C 24 08 48 89 74 24 10 57 48 83 EC 20 48 8B F1 E8 69 1D 24 FF E8 C4 EC C7 FE 4C 8B C0 45 33 C9 33 D2 B9 70 04 00 00 E8 42 D5 C7 FE
DESC: What it is: An initialize function for the Variant and Criterion finder window. When it runs: During the early setup phase before the finder is ready to use. Why you would care: Use it if you want to inspect or change finder UI state before it becomes active.
----------------------------------------
NAME: AddonVVDFinder_Finalizer
SIG:  48 89 5C 24 08 57 48 83 EC 20 48 8B B9 38 02 00 00 48 8B D9 48 85 FF 74 21 48 8D 4F 70 E8 8E F0 07 00 BA 70 04 00 00 48 8B CF E8 19 F2 8B 00
DESC: What it is: A cleanup function for the Variant and Criterion finder window. When it runs: When the game is finished with that window. Why you would care: Use it if you want to track or react to finder UI cleanup.
----------------------------------------
NAME: AddonVVDVoteRoute_ctor
SIG:  40 53 48 83 EC 20 48 8B D9 E8 62 B2 23 FF 80 8B A3 01 00 00 08 48 8D 05 CC 59 D6 00 80 8B A0 01 00 00 20 80 8B A5 01 00 00 02 81 8B C8 01 00 00 00 00 01 00
DESC: What it is: A constructor for the Variant route voting window object. When it runs: Before route voting is shown. Why you would care: Use it if you want an early hook for route-vote UI creation.
----------------------------------------
NAME: AddonVVDVoteRoute_Initialize
SIG:  40 53 48 83 EC 20 48 8B D9 E8 72 EA 23 FF BA 01 00 00 00 41 B8 9E 00 00 00 48 8B CB E8 DF F4 23 FF E8 BA B9 C7 FE 33 D2 4C 8B C0 45 33 C9
DESC: What it is: An initialize function for the route voting window. When it runs: During the early setup phase before route voting is ready to use. Why you would care: Use it if you want to inspect or change the voting UI before it becomes active.
----------------------------------------
NAME: AddonVVDVoteRoute_Finalizer
SIG:  40 53 48 83 EC 20 48 8B D9 48 8B 89 38 02 00 00 48 85 C9 74 15 48 8B 01 BA 01 00 00 00 FF 10 48 C7 83 38 02 00 00 00 00 00 00 45 33 C9
DESC: What it is: A cleanup function for the route voting window. When it runs: When the game is finished with that window. Why you would care: Use it if you want to track or react to route-vote UI cleanup.
----------------------------------------
NAME: AddonVVDVoteRoute_vf50
SIG:  40 57 48 83 EC 20 48 8B B9 38 02 00 00 48 85 FF 74 32 48 8B 4F 18 48 89 5C 24 30 48 8B 5F 08 48 8B 01 FF 50 78 48 89 83 F8 00 00 00 45 33 C9
DESC: What it is: An extra helper function used by the route voting window. When it runs: While the voting window is active and handling its own internal behavior. Why you would care: Use it if you need another hook near route-vote UI behavior.
----------------------------------------




