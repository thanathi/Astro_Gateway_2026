ข้อมูลสำหรับโน้ตบุ๊ก — Astro Gateway 2026
==========================================

Gaia/ — แค็ตตาล็อก Gaia DR3 สำรอง
---------------------------------
ดึงผ่าน VizieR (ตาราง I/355/gaiadr3) เมื่อ 5 ต.ค. 2569
โน้ตบุ๊กดึงข้อมูลสดจาก VizieR ก่อน และใช้ไฟล์เหล่านี้เมื่อเน็ตในห้องเรียนใช้ไม่ได้

  ไฟล์                     กระจุก           ศูนย์กลาง (RA, Dec)   รัศมี   เงื่อนไข             จำนวนดาว
  pleiades_gaia_dr3.csv    ดาวลูกไก่ (M45)   56.75, +24.12         2.5°    G < 17, ϖ/σ > 10    20,405
  ngc2516_gaia_dr3.csv     NGC 2516         119.53, −60.80        1.0°    G < 17, ϖ/σ > 10    10,331
  praesepe_gaia_dr3.csv    รังผึ้ง (M44)      130.10, +19.67        1.5°    G < 17, ϖ/σ > 10     6,094
  m67_gaia_dr3.csv         M67              132.846, +11.814      0.6°    G < 18, ϖ/σ > 5      2,515
  ngc188_gaia_dr3.csv      NGC 188          12.11, +85.24         0.5°    G < 18, ϖ/σ > 5      3,102

คอลัมน์: source_id, ra, dec, parallax, parallax_error, pmra, pmdec, phot_g_mean_mag,
         phot_bp_mean_mag, phot_rp_mean_mag, bp_rp, radial_velocity


XSL/ — สเปกตรัมดาวฤกษ์ (X-shooter Spectral Library DR2)
--------------------------------------------------------
ดาวน์โหลดจาก xsl.u-strasbg.fr/dr2_fits/ เมื่อ 8 ต.ค. 2569
ค่าพารามิเตอร์ดาวจาก Arentsen et al. (2019, A&A 627, A138)

  xsl_spectrum_X0832_uvb.fits, _vis.fits   HD 39833   ดาวแคระ G3V            Teff 5,802 K  log g 4.37  [Fe/H] +0.13
  xsl_spectrum_X0142_uvb.fits, _vis.fits   HD 160346  ดาวแคระ K3V            Teff 4,926 K  log g 4.68  [Fe/H] +0.02
  xsl_spectrum_X0070_uvb.fits, _vis.fits   HD 19445   ดาวแคระโลหะน้อย G2V Fe−3  Teff 5,928 K  log g 4.02  [Fe/H] −2.04

แต่ละดาวมี 2 ไฟล์: แขน UVB (300–556 nm) และ VIS (534–1020 nm)
คอลัมน์ WAVE [nm], FLUX, ERR [erg/s/cm²/Å]
ฟังก์ชัน load_xsl ในโน้ตบุ๊กต่อ 2 แขนที่ 5,550 Å และปรับระดับแขน VIS ให้ต่อกัน
(ช่วงรอยต่อ 5,350–5,550 Å มีสัญญาณรบกวนจาก dichroic)


SDSS/ — สเปกตรัมกาแล็กซี (Sloan Digital Sky Survey DR17)
--------------------------------------------------------
  spec-0531-52028-0573.fits   SDSS J140102.07+025242.5   กาแล็กซี starburst  z = 0.25196   (โน้ตบุ๊ก 02)
  spec-0394-51913-0075.fits   SDSS J005527.46−002148.8   กาแล็กซี starburst  z = 0.16742   (ภารกิจเดิม — ไม่ได้ใช้แล้ว)

ที่มา: dr17.sdss.org/sas/dr17/sdss/spectro/redux/26/spectra/lite/<plate>/


Cepheid/ — ดาวเซเฟอิดในเมฆแมเจลแลนใหญ่ (LMC)
---------------------------------------------
  OGLE-LMC-CEP-0728.dat, -1508.dat, -2491.dat
      คาบ 3.084, 1.309, 1.066 วัน · คอลัมน์: HJD−2450000, I (mag), error
      ที่มา: OGLE-IV OCVS  www.astrouw.edu.pl/ogle/ogle4/OCVS/lmc/cep/phot/I/

  TIC_277014840.csv, TIC_389505835.csv, TIC_30758596.csv, TIC_280039063.csv, TIC_389323821.csv
      ดาวเซเฟอิด 5 ดวงจาก TESS sector 1–2 (ทุก 30 นาที) · คอลัมน์: id, time (BTJD), mag, mag_err
      ที่มา: ดาวน์โหลดจาก TESSExtractor (www.tessextractor.app — เครื่องมือดึงกราฟแสงจากภาพเต็มเฟรมของ TESS)
             เมื่อ 25 มี.ค. 2569 (บันทึกใน metadata ของไฟล์ต้นฉบับใน POSN_SK ชื่อ 1.csv–5.csv) · ไม่มีในคลังข้อมูลสาธารณะ
      ค่า mag ถูกตั้งศูนย์ให้ค่ามัธยฐานเท่ากับ Tmag ในแค็ตตาล็อก TIC (ไม่ใช่การวัดที่ปรับเทียบแล้ว)
      และแอมพลิจูดเล็กกว่าจริงเพราะแสงดาวข้างเคียงปน (พิกเซล TESS กว้าง 21 พิลิปดา)

      ไฟล์                TIC         OGLE (ยืนยันจากตำแหน่ง ≤ 15")   คาบ OGLE (วัน)   <I> OGLE   Tmag (TIC)
      TIC_277014840.csv   277014840   OGLE-LMC-CEP-2491              1.0659           16.73      16.98
      TIC_389505835.csv   389505835   OGLE-LMC-CEP-3089              2.0055           15.93      16.27
      TIC_30758596.csv    30758596    OGLE-LMC-CEP-0728              3.0837           15.32      15.48
      TIC_280039063.csv   280039063   OGLE-LMC-CEP-2066              7.4424           14.09      14.29
      TIC_389323821.csv   389323821   OGLE-LMC-CEP-2979              17.7953          13.68      13.88
      (targets.txt ต้นฉบับมี TIC 31183631 = OGLE-LMC-CEP-0986, คาบ 31.06 วัน ซึ่งถูก comment ออก — ยาวกว่า 1 sector)
      ทุกดวงเป็นเซเฟอิดแบบ fundamental mode (F)


TESS/ — กราฟแสง TESS ทุก 2 นาที (SPOC, PDCSAP) — โน้ตบุ๊ก 03 ส่วน B และภารกิจ (โน้ตบุ๊ก 04)
--------------------------------------------------------------------------------
  ไฟล์ชื่อ tess<เวลา>-s<sector>-<TIC 16 หลัก>-<รุ่น>-s_lc.fits · 1 sector ต่อดาว ดาวน์โหลดจาก MAST เมื่อ 11 ต.ค. 2569
  (โน้ตบุ๊กดาวน์โหลดเองจาก mast.stsci.edu/api/v0.1/Download/file?uri=mast:TESS/product/<ชื่อไฟล์> ถ้าไม่มีไฟล์ในโฟลเดอร์นี้)
  ตัวอย่างโน้ตบุ๊ก 03: HD 209458 b (TIC 420814525, sector 56)
  ภารกิจ (17 ดวง): WASP-17 b, WASP-121 b, WASP-12 b, WASP-19 b, WASP-18 b, HD 189733 b, WASP-43 b, WASP-80 b, WASP-126 b, GJ 436 b, GJ 3470 b, TOI-849 b, TOI-270 c, pi Men c, LHS 3844 b, GJ 1132 b, LTT 1445 A b
  ภารกิจท้าทาย: TOI-4597.01, TOI-1717.01, TOI-1951.01 (ผู้สมัครดาวเคราะห์ TFOPWG = PC)
      และ TIC 393636596 sector 24 — ดาวคู่อุปราคา คาบ 0.8792 วัน (ตัวอย่างสัญญาณที่ไม่ใช่ดาวเคราะห์)
  รายชื่อ TIC, sector และค่าที่ตีพิมพ์ของทุกดวงอยู่ใน Lectures/_build/exoplanets.py (ค่าจาก NASA Exoplanet Archive)


Exoplanets/ — รายชื่อดาวเคราะห์ผ่านหน้าที่ยืนยันแล้ว (โน้ตบุ๊ก 04 ขั้น M6)
--------------------------------------------------------------------------------
  confirmed_transiting_planets.csv
      4,780 ดวง จาก NASA Exoplanet Archive ตาราง pscomppars (discoverymethod = Transit, มีคาบและรัศมี) ดึงเมื่อ 11 ต.ค. 2569
      คอลัมน์: pl_name, pl_orbper (วัน), pl_rade (รัศมีโลก), pl_bmasse (มวลโลก), disc_facility, disc_year


K2/ — ดาวเคราะห์ K2-24 (โน้ตบุ๊ก 03 ส่วน B เดิม — ตอนนี้ใช้ HD 209458 b จาก TESS แทน)
-----------------------------------------
  hlsp_everest_k2_llc_203771098-c02_kepler_v2.0_lc.fits
      K2-24 (EPIC 203771098) กราฟแสง K2 campaign 2 ทุก 30 นาที (EVEREST v2)
      ที่มา: MAST HLSP  archive.stsci.edu/hlsps/everest/v2/c02/203700000/71098/

  epic203771098.csv
      ความเร็วแนวเล็งของ K2-24 จาก Keck/HIRES · คอลัมน์: t (BJD−2454833), vel, errvel [m/s]
      ที่มา: github.com/California-Planet-Search/radvel (example_data)


Stars/ — ลำดับดาวแคระมาตรฐาน: ชนิดสเปกตรัม สี และอุณหภูมิ (โน้ตบุ๊ก 02 ขั้น A3, ภาพในสไลด์)
--------------------------------------------------------------------------------
  dwarf_sequence_mamajek.csv
      "A Modern Mean Dwarf Stellar Color and Effective Temperature Sequence" (E. Mamajek) ฉบับ 2022.04.16
      ส่วนใหญ่ตีพิมพ์ใน Pecaut & Mamajek (2013, ApJS 208, 9) ตาราง 5 — ให้อ้างอิงบทความนี้
      ชนิด O3V–M9.5V (87 ชนิด) · คอลัมน์: SpT, Teff (K), B_V, BP_RP (Gaia DR2; มีตั้งแต่ B9V), M_G, Mass (M☉)
      ที่มา: www.pas.rochester.edu/~emamajek/EEM_dwarf_UBVIJHK_colors_Teff.txt ดาวน์โหลดเมื่อ 11 ต.ค. 2569
      สี BP−RP ของดาว XSL 3 ดวงในโน้ตบุ๊กจาก Gaia DR3 (VizieR I/355/gaiadr3)


Isochrones/ — ไอโซโครน PARSEC สำหรับหาอายุกระจุกดาว (โน้ตบุ๊ก 01 ส่วน 7.1 และข้อ 8)
--------------------------------------------------------------------------------
  parsec_gaia_dr3.csv
      แบบจำลอง PARSEC v1.2S (Bressan et al. 2012) แถบ Gaia EDR3/DR3 (Vega mag) · IMF Kroupa · ไม่มีฝุ่น (A_V = 0)
      [M/H] = −2.0, −1.5, −1.0, −0.5, 0.0, +0.5 · log อายุ 6.6–10.0 ทุก 0.1 (35 อายุ)
      ตัดช่วง TP-AGB และหลัง AGB ออก (label 0–7: ก่อนเกิด, ลำดับหลัก, ดาวยักษ์ย่อย, ดาวยักษ์แดง, เผาฮีเลียม, AGB ช่วงต้น)
      คอลัมน์: MH, logAge, Mini (มวลตั้งต้น M☉), label (ช่วงวิวัฒนาการ), G (M_G), BP_RP
      ที่มา: stev.oapd.inaf.it/cgi-bin/cmd (CMD 3.9) ดาวน์โหลดเมื่อ 11 ต.ค. 2569 (ไฟล์เต็ม PARSEC.dat ในโฟลเดอร์นี้
             ไม่ได้ใส่ในชุดที่แจก) แปลงด้วย _build/fetch_isochrones.py
      ผลของฝุ่นในโน้ตบุ๊ก (คำนวณจากไอโซโครนโลหะเท่าดวงอาทิตย์ที่ A_V = 0 และ 1, กฎ Cardelli R_V = 3.1):
          A_G = A_V × (0.959 − 0.125 × (BP−RP)₀)     E(BP−RP) = A_V × (0.465 − 0.059 × (BP−RP)₀)
      ค่า A_V ของแต่ละกระจุกจาก Cantat-Gaudin et al. (2020) คอลัมน์ AVNN

ที่มาของไฟล์
------------
Gaia: ดึงจาก VizieR · Cepheid, TESS, SDSS spec-0531: คัดลอกจาก Teaching/POSN_SK เมื่อ 8 ต.ค. 2569
XSL, K2, SDSS spec-0394: ดาวน์โหลดเมื่อ 8 ต.ค. 2569
