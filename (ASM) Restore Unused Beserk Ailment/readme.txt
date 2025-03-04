----------------------------------------
  (ASM) Restore Unused Beserk Ailment
----------------------------------------

The Berserk status is an unused ailment in Super Mario RPG.
What is does, by default, is forces the one afflicted with the ailment to use a physical attack on a random target, without disgression of being a friend, themselves, or foe.
This patch fixes being able to apply the ailment on allies, and provides an aestheic fix in the ASM (makes the character's head bob up and down).
Allies still need a battle portrait animation sequence, which this patch does not apply. The sequence is "06" in the editor.

It works only on allies (for now). If applied to a monster, the monster always misses (this is a bug from the original game).

This does /not/ change anything outside of the ASM, so it is safe to apply to any ROM file.
If, for any reason, you want to apply the code in the patch manually, the ASM is at the bottom of this document.



-------------------------------------
    Changes you need to implement
-------------------------------------
When an ally has this ailment, the battle portraits (Sprites 40-44) change to sequence 06. This portrait is not included in this patch, and will look garbled without an update.
 

 
------------
    ASM
------------

C2/BDE8 EA EA		; Removes code that originally filtered out the unused ailment

C2/BE44 EA EA		; Removes code that originally filtered out the unused ailment

C2/A135 20 34 AC	; JSR to target random only from pool of mortal monsters on battlefield 
			; Notes: $C2/AB96 targets random ally (including themselves), $C2/AC34 targets random monster (including themselves), $C2/AD25 targets random anyone on field (including themselves)

C2/4607 E2 20 
	BF 43 00 7E	; Check for ailment timer
	C9 04		; see if ally has timer of 4 (aka ailment had just gotten applied)
	F0 45		; jump if not equal
	
	BF 40 00 7E	; Check for all ailments
	F0 3D		; branch to end if not equal
	
	89 02 		; Check for Sleep 
	F0 0A  		; jump if not equal
	A9 08 		; sprite looping bit flag?
	85 E0 
	A9 06 		; sequence 06
	85 E4 		; Sets new sequence
	80 2F 		; jump to end
	
	89 08 		; Check for Fear
	F0 0A		; jump to next check if not equal
	A9 08		; sprite looping bit flag?
	85 E0
	A9 0B		; sequence 11 (fear shaking)
	85 E4 		; Set new sequence
	80 21 		; jump to end
	
	89 01 		; Check for Mute
	F0 06		; jump to next check if not equal
	A9 0D 		; sequence 13 (Mute slouch)
	85 E4 		; Set new sequence
	80 17		; jump to end

	89 04 		; Check for Poison
	F0 06		; jump to next check if not equal
	A9 3C 		; palette 4 (0x0F * 4)
	85 EE 		; Set new palette
	80 0D 		; jump to end
	
	89 10 		; Check for Berserk
	A9 08		; sprite looping bit flag?
	85 E0 
	A9 07 		; sequence 07 (head bobbing up-and-down)
	85 E4 		; Sets new sequence
	
	EA		; NOP
	EA 		;
	EA 		;
C2/4654 C2 20
