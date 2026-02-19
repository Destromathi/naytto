Grimhall on Pythonilla toteutettu tekstipohjainen roolipeli, jossa pelaaja matkustaa alueelta toiselle, taistelee vihollisia vastaan, kerää parempia varusteita ja kohtaa lopulta linnan tyrannin.

Peli sisältää:

Vuoropohjaisen taistelujärjestelmän
-Kriittiset osumat

-Varusteet ja inventaarion

-Satunnaiset vihollisrepliikit

-Boss-taistelun

-ANSI-värikoodatun taistelun

▶️ Käynnistäminen

-python main.py

Vaatimukset

-Python 3.x

-Ei ulkoisia kirjastoja

🎮 Pelin kulku


-Pelaaja aloittaa Grimhall villagesta

-Jokaisella alueella käydään 3 taistelua

-Viimeisessä alueessa kohdataan boss

-Jos pelaaja selviytyy → voitto

-Jos HP putoaa nollaan → Game Over

📂 Projektirakenne

🧍 player.py

Sisältää Player-luokan.

Ominaisuudet

-name

-hp / max_hp (30 alussa)

-weapon

-armor

-inventory

Toiminnot

-is_alive() – Tarkistaa elossaolon

-take_damage(dmg) – Vähentää armorin perusteella

-heal() – Parantaa 8–16 HP

-show_equipped() – Näyttää varusteet

-show_inventory() – Näyttää tavarat

-equip(index) – Varustaa valitun esineen

Pelaaja aloittaa:

-Rusty Sword (1–4 dmg)

-Leather Armor (+1 def)

⚔️ fight.py

Hallitsee koko taistelusilmukan.

-Pelaajan komennot

-Komento	Toiminto

-attack	Normaali hyökkäys

-special	Mahdollinen kriittinen osuma

-inventory	Avaa inventaarion

-gear	Näyttää varusteet

-heal	Käyttää parannuksen

-Taistelumekaniikka

-Vahinko lasketaan utils.roll_damage() avulla

-special_hit() tarkistaa kriittisen osuman

-Kriittinen osuma = 2x damage

-Vihollisen defense vähentää pelaajan vahinkoa

-Pelaajan armor vähentää vihollisen vahinkoa

-Vihollinen puhuu satunnaisesti (speak())

🧟 enemies.py

Sisältää Enemy-luokan ja vihollisten luontifunktion.

Enemy-ominaisuudet

-name

-hp

-min_dmg, max_dmg

-defense

-loot

-dialogue

Metodit

-is_alive()

-attack()

-generate_loot()

-speak()

🌍 Alueet ja viholliset
🏘️ Grimhall village

Ei vihollisia

🌲 Darkwood

-Goblin

-Wolf

-Forest Spider

🕳️ Cave

-Giant Rat

-Bat Swarm

-Cave Spider

❄️ Tundra

-Ice Bear

-Frost Wolf

-Snow Spider

🏰 Old Castle

-Castle Guard

-Armored Knight

-Dark Archer

🩸 Abandoned Dungeon (Boss)

-Castle Lord "Ironhand"

-200 HP

-Korkea defense

-Vahva hyökkäys

-Statseja vahvistetaan main.py-tiedostossa

🗡️ items.py

Sisältää aseet ja haarniskat.

-Weapon

-name

-min_dmg

-max_dmg

-crit_chance (oletus 10%)

-Armor

-name

-defense

Aseet

Nimi	Damage

-Rusty Sword	1–4

-Basic Sword	2–5

-Iron Sword	3–7

-Steel Sword	5–10

-Legendary Sword	8–15

Haarniskat

Nimi	Defense

-Leather Armor	+1

-Hide Armor	+2

-Iron Armor	+3

-Steel Armor	+5

-Legendary Armor	+8

🌍 world.py

Sisältää pelimaailman rakenteen.

rooms-sanakirja

Jokaisella alueella on:

description – tekstikuvaus

enemies – lista mahdollisista vihollisista

next – seuraava alue

Aluejärjestys

Grimhall village
→ Darkwood
→ Cave
→ Tundra
→ Old Castle
→ Abandoned Dungeon

🎲 utils.py

Sisältää apufunktiot:

roll_damage(weapon) – Arpoo vahingon weaponin rajojen mukaan

special_hit(chance) – Palauttaa True jos kriittinen osuma osuu

🎨 Visuaaliset ominaisuudet

Taistelu käyttää ANSI-värikoodeja:

🔵 Pelaajan tiedot

🟢 Pelaajan aiheuttama vahinko

🔴 Vihollisen aiheuttama vahinko

🟡 Vihollisen puhe

🏆 Voitto

Jos voitat viimeisen bossin:

"You have conquered Grimhall..."

                                                !!Lue GUIDE!!
