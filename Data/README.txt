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


SDSS/ — สเปกตรัมกาแล็กซี (Sloan Digital Sky Survey DR17)
--------------------------------------------------------
  spec-0531-52028-0573.fits   SDSS J140102.07+025242.5   กาแล็กซี starburst  z = 0.25196   (โน้ตบุ๊ก 02)
  spec-0394-51913-0075.fits   SDSS J005527.46−002148.8   กาแล็กซี starburst  z = 0.16742   (ภารกิจ 2)

ที่มา: dr17.sdss.org/sas/dr17/sdss/spectro/redux/26/spectra/lite/<plate>/


Cepheid/ — ดาวเซเฟอิดในเมฆแมเจลแลนใหญ่ (LMC)
---------------------------------------------
  OGLE-LMC-CEP-0728.dat, -1508.dat, -2491.dat
      คาบ 3.084, 1.309, 1.066 วัน · คอลัมน์: HJD−2450000, I (mag), error
      ที่มา: OGLE-IV OCVS  www.astrouw.edu.pl/ogle/ogle4/OCVS/lmc/cep/phot/I/

  TIC_277014840.csv, TIC_389505835.csv, TIC_30758596.csv, TIC_280039063.csv, TIC_389323821.csv
      ดาวเซเฟอิด 5 ดวงจาก TESS sector 1–2 (ทุก 30 นาที) · คอลัมน์: id, time (BTJD), mag, mag_err
      ที่มา: ดาวน์โหลดจาก TESSExtractor (www.tessextractor.app — เครื่องมือดึงกราฟแสงจากภาพเต็มเฟรมของ TESS)
             เมื่อ 25 มี.ค. 2569
      ค่า mag ถูกตั้งศูนย์ให้ค่ามัธยฐานเท่ากับ Tmag ในแค็ตตาล็อก TIC (ไม่ใช่การวัดที่ปรับเทียบแล้ว)
      และแอมพลิจูดเล็กกว่าจริงเพราะแสงดาวข้างเคียงปน (พิกเซล TESS กว้าง 21 พิลิปดา)

      ไฟล์                TIC         OGLE			   คาบ OGLE (วัน)   <I> OGLE   Tmag (TIC)
      TIC_277014840.csv   277014840   OGLE-LMC-CEP-2491              1.0659           16.73      16.98
      TIC_389505835.csv   389505835   OGLE-LMC-CEP-3089              2.0055           15.93      16.27
      TIC_30758596.csv    30758596    OGLE-LMC-CEP-0728              3.0837           15.32      15.48
      TIC_280039063.csv   280039063   OGLE-LMC-CEP-2066              7.4424           14.09      14.29
      TIC_389323821.csv   389323821   OGLE-LMC-CEP-2979              17.7953          13.68      13.88
      ทุกดวงเป็นเซเฟอิดแบบ fundamental mode (F)


TESS/ — ดาวคู่อุปราคา TIC 393636596
----------------------------------------------
  tess2020106103520-s0024-0000000393636596-0180-s_lc.fits
      TESS sector 24 ทุก 2 นาที · คาบ 0.8794 วัน
      ที่มา: MAST  mast:TESS/product/...


K2/ — ดาวเคราะห์ K2-24
-----------------------------------------
  hlsp_everest_k2_llc_203771098-c02_kepler_v2.0_lc.fits
      K2-24 (EPIC 203771098) กราฟแสง K2 campaign 2 ทุก 30 นาที (EVEREST v2)
      ที่มา: MAST HLSP  archive.stsci.edu/hlsps/everest/v2/c02/203700000/71098/

  epic203771098.csv
      ความเร็วแนวเล็งของ K2-24 จาก Keck/HIRES · คอลัมน์: t (BJD−2454833), vel, errvel [m/s]
      ที่มา: github.com/California-Planet-Search/radvel (example_data)


ที่มาของไฟล์
------------
Gaia: ดึงจาก VizieR · Cepheid, TESS, SDSS spec-0531: จากข้อมูลเดิม
XSL, K2, SDSS spec-0394: ดาวน์โหลดเมื่อ 8 ต.ค. 2569
