SIGNATURE FILE SEARCH GUIDE
============================================================
This is the easiest way to search the signature files.
1. Search by category first.
   The files are grouped with lines that start like this:
   CATEGORY: Quest Interaction Gates - Core Quest State Gates
   CATEGORY: PvP Status and Buff UI
   CATEGORY: Ground-Targeting Internals
2. If you want a whole topic, search for `CATEGORY:`.
   Examples:
   CATEGORY: PvP
   CATEGORY: Quest
   CATEGORY: Housing
   CATEGORY: Ground-Targeting
   CATEGORY: UI Addon
3. After you find the category you want, go down the list under it.
   Each entry is stored like this:
   ----------------------------------------
   NAME: Example_Name
   SIG:  48 89 5C 24 ?? ...
   DESC: Short explanation of what it does.
   ----------------------------------------
4. If you want one exact thing, search by `NAME:`.
   Examples:
   NAME: QuestManager_IsQuestAccepted
   NAME: PacketDispatcher_HandleQuestCompletePacket
   NAME: ActionManager_StartAreaTargetingMode
   NAME: HousingManager_SetTemporaryObject
5. If you only know the system and not the exact function, search by a keyword.
   Good examples:
   Quest
   PvP
   Housing
   Addon
   Journal
   Target
   EventFramework
   PacketDispatcher
6. Best workflow:
   Search `CATEGORY:` first.
   Then look under that section.
   Then search `NAME:` if you want one exact signature.
Examples
----------------------------------------
If someone wants PvP signatures:
Search for:
`CATEGORY: PvP`
If someone wants quest signatures:
Search for:
`CATEGORY: Quest`
If someone wants housing placement signatures:
Search for:
`CATEGORY: Housing`
If someone wants ground-targeting signatures:
Search for:
`CATEGORY: Ground-Targeting`
If someone wants one exact function:
Search for:
`NAME: QuestManager_IsQuestAccepted`
Quick Tip
----------------------------------------
`CATEGORY:` is for broad browsing.
`NAME:` is for exact lookup.
`SIG:` is the actual signature.
`DESC:` tells you what the signature is for.
