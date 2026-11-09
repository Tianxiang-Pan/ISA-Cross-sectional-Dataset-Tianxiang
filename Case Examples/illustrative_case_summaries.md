# Illustrative ICB Cases

Verified against `matched_caliper` (crisis-dyad level analytic sample) and
`ICBdy_step16` (intervener-level data, pre-aggregation), and checked for a
**genuine** single-intervener match -- i.e. the same country satisfies all
of the relevant conditions, not different countries each satisfying one
condition. See `R Code/ICB Case Finder.Rmd` for the code and
`case_summary_with_interveners.csv` for the full list.

---

## Type 1: Democratic intervener with ties to both sides, long-term success

### Ecuador/Peru Border War V (1995) -- Argentina, Brazil, Chile, United States

Data: `crisno` 413, `crdynum` 834, intervener-coded `regime_type_int = 1`,
`ties_to_both_sides = 1` for all four states individually (not just in
aggregate), `outesr = 1` (long-term tension reduction), `forout = 1`
(short-term agreement also reached), `state_capacity_int` ranges from
0.003 (Chile) to 0.140 (United States).

All four are the 1942 Rio Protocol guarantor powers, bound by that treaty
to both Ecuador and Peru since 1942 (the protocol itself followed the
1941 war between the two). When the 1995 Cenepa War broke out, the
guarantors issued the Itamaraty Declaration (17 February 1995) calling
for troop separation and demilitarization, and launched the Military
Observer Mission Ecuador-Peru (MOMEP, from 12 March 1995, led by the
United States), which oversaw the withdrawal of roughly 3,000 Ecuadorian
and 2,000 Peruvian troops. Guarantor-facilitated negotiations continued
through 1998, producing the Presidential Act of Brasilia, which formally
ended the long-standing border dispute. This is a clean, well-documented
case of four democratic guarantor states with longstanding treaty ties to
both disputants delivering a durable settlement.

Sources: [Cenepa War (Wikipedia)](https://en.wikipedia.org/wiki/Cenepa_War); [Brasilia Presidential Act (Wikipedia)](https://en.wikipedia.org/wiki/Brasilia_Presidential_Act); [Better Evidence Project](https://bep.carterschool.gmu.edu/resolving-the-militarised-territorial-dispute-between-ecuador-and-peru/)

### Aegean Sea I (1976) -- United States

Data: `crisno` 272, `crdynum` 623, intervener United States,
`regime_type_int = 1`, `ties_to_both_sides = 1`, `state_capacity_int` =
0.142, `outesr = 1` (long-term success) despite `forout = 0` (no
agreement at termination).

Greece and Turkey, both NATO allies of the United States, clashed over
continental-shelf rights in the Aegean after Turkish seismic survey
vessels entered disputed waters; Greece brought the dispute to the UN
Security Council and the ICJ in August 1976. Contemporary reporting
confirms US diplomatic engagement with both Greek and Turkish foreign
ministers over the Aegean and the related Cyprus dispute; we could not
independently confirm the specific content of US proposals, so this
detail is worth a quick check against the ICB narrative summary before
citing specifics in text. The data pattern -- no immediate agreement
(`forout = 0`) but tension reduction over the following years (`outesr =
1`) -- fits a "US as NATO patron with ties to both sides, slow-burn
success" story.

Sources: [UN Security Council Resolution 395 (Wikipedia)](https://en.wikipedia.org/wiki/United_Nations_Security_Council_Resolution_395); [ICJ, Aegean Sea Continental Shelf case](https://www.icj-cij.org/index.php/case/62)

---

## Type 2: Weak democratic intervener, short-term failure

Note: "weak" is defined on `state_capacity_int` (NMC/CINC, a
year-normalized share of world capability) rather than raw
`military_expenditure_int`, because the latter is nominal and trends
upward across the 20th century (r = 0.41 with year), while CINC does not
(r = -0.14). Bottom-25% CINC threshold in the matched sample: 0.0111.

### Suez Nationalization War (1956) -- Australia

Data: `crisno` 152, `crdynum` 413 (one of five matching dyads in this
crisis), intervener Australia, `regime_type_int = 1`,
`state_capacity_int` = 0.0069 (well below the 0.0111 threshold),
`forout = 0`, `outesr = 0` (failed both short- and long-term).

Australian PM Robert Menzies chaired the five-nation "Suez Committee"
(Australia, Ethiopia, Iran, Sweden, United States), which carried the
18-power plan for international control of the canal to Cairo and met
Nasser between 3-9 September 1956. The mission ended without agreement
and formally disbanded on 10 September; Menzies called the situation
"very, very grave." Australia subsequently backed Britain through the
invasion, and Egypt severed relations with Australia. This is a clear,
historically prominent failure case, and Australia's low global CINC
share in 1956 (a middle power acting as lead diplomat for a coalition of
mostly larger states) fits the "weak democratic intervener struggled"
story well.

Sources: [Suez Committee and Menzies Mission, FRUS 1955-57 v.16, doc. 128](https://history.state.gov/historicaldocuments/frus1955-57v16/d128); [International Affairs, "Tina Turner, Menzies and Suez"](https://www.internationalaffairs.org.au/?p=19034)

### Khorramshahr (1982) -- Sweden

Data: `crisno` 335, `crdynum` 699, intervener Sweden,
`regime_type_int = 1`, `state_capacity_int` = 0.0034 (well below
threshold), `forout = 0`, `outesr = 0`.

Sweden is coded as a diplomatic intervener in this Iran-Iraq War crisis
and is, on paper, a clean case: genuinely weak by any measure (not just
low global CINC share, unlike e.g. Israel in another near-miss case),
and both outcome variables failed. Former Swedish PM Olof Palme did serve
as UN special envoy mediating the Iran-Iraq War, but the missions we
could verify in open sources are from November 1980 through February
1981 (he left Tehran after a third unsuccessful attempt), not specifically
tied to the May 1982 recapture of Khorramshahr. **We were not able to
verify Swedish diplomatic activity specifically tied to this 1982
episode** -- before citing this case by name, check the ICB case
narrative/codebook entry for crisis 335 to confirm what Swedish
involvement the coders had in mind.

Sources: [Olof Palme (Wikipedia)](https://en.wikipedia.org/wiki/Olof_Palme); [Christian Science Monitor, "UN envoy leaves Iran; Tehran adamant on war" (1981)](https://www.csmonitor.com/1981/0223/022334.html)
