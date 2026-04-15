[index.html](https://github.com/user-attachments/files/26763724/index-19.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GO Dental – Insurance Verification</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
:root {
  --green:   #1D9E75;
  --dark:    #0F6E56;
  --tint:    #E6F5EF;
  --tint2:   #f0faf6;
  --warn:    #1D9E75;
  --warn-bg: #E6F5EF;
  --warn-bd: #B2D8C8;
  --border:  #E2E8E5;
  --bg:      #F4F7F5;
  --text:    #1A2421;
  --muted:   #7A9089;
  --radius:  6px;
}
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: 'DM Sans', sans-serif; background: var(--bg); color: var(--text); font-size: 13px; -webkit-font-smoothing: antialiased; }
.page { max-width: 960px; margin: 0 auto; background: #fff; min-height: 100vh; border-left: 1px solid var(--border); border-right: 1px solid var(--border); }

/* TOOLBAR */
.toolbar { position: sticky; top: 0; z-index: 200; background: #111E1A; padding: 0 28px; height: 48px; display: flex; align-items: center; justify-content: space-between; }
.toolbar-brand { display: flex; align-items: center; gap: 10px; }
.toolbar-logo { width: 26px; height: 26px; background: var(--green); border-radius: 50%; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
.toolbar-logo span { font-size: 9px; font-weight: 700; color: #fff; letter-spacing: -.5px; }
.toolbar-name { font-size: 12px; font-weight: 600; color: rgba(255,255,255,.7); letter-spacing: .04em; text-transform: uppercase; }
.print-btn { background: var(--green); color: #fff; border: none; padding: 7px 18px; border-radius: var(--radius); cursor: pointer; font-size: 12px; font-weight: 600; font-family: inherit; display: inline-flex; align-items: center; gap: 7px; transition: background .15s; }
.print-btn:hover { background: var(--dark); }

/* HEADER */
.header { background: var(--green); padding: 22px 28px 20px; display: flex; align-items: flex-start; justify-content: space-between; gap: 20px; }
.header-left { display: flex; align-items: center; gap: 14px; }
.logo-circle { width: 46px; height: 46px; background: #fff; border-radius: 50%; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
.logo-circle span { font-size: 14px; font-weight: 700; color: var(--green); letter-spacing: -1px; }
.header-title { color: #fff; font-size: 20px; font-weight: 700; line-height: 1.2; }
.header-sub { color: rgba(255,255,255,.7); font-size: 11px; margin-top: 3px; }
.verified-block { display: flex; flex-direction: column; gap: 4px; align-items: flex-end; }
.verified-label { font-size: 10px; font-weight: 600; color: rgba(255,255,255,.7); text-transform: uppercase; letter-spacing: .08em; }
.verified-input { background: transparent; border: none; border-bottom: 1px solid rgba(255,255,255,.4); border-radius: 0; padding: 4px 0; color: #fff; font-family: inherit; font-size: 13px; font-weight: 700; width: 220px; outline: none; text-transform: uppercase; letter-spacing: .04em; text-align: right; }
.verified-input::placeholder { color: rgba(255,255,255,.4); font-weight: 400; text-transform: none; letter-spacing: 0; }
.verified-input:focus { border-bottom-color: rgba(255,255,255,.8); }

/* META STRIP */
.meta-strip { display: grid; grid-template-columns: repeat(6, 1fr); border-bottom: 1px solid var(--border); }
.meta-cell { padding: 10px 14px; border-right: 1px solid var(--border); }
.meta-cell:last-child { border-right: none; }
.meta-lbl { font-size: 9px; font-weight: 700; color: var(--muted); text-transform: uppercase; letter-spacing: .07em; margin-bottom: 4px; }
.meta-val { font-size: 12px; color: var(--text); font-weight: 500; outline: none; min-height: 16px; }
.meta-val:focus { color: var(--green); }

/* SECTIONS */
.section { padding: 20px 28px; border-bottom: 1px solid var(--border); }
.section:last-child { border-bottom: none; }
.sec-header { display: flex; align-items: center; gap: 9px; margin-bottom: 14px; }
.sec-num { width: 20px; height: 20px; border-radius: 50%; background: var(--green); color: #fff; font-size: 10px; font-weight: 700; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
.sec-title { font-size: 12px; font-weight: 700; color: var(--dark); text-transform: uppercase; letter-spacing: .08em; flex: 1; }
.sec-header::after { content: ""; flex: 1; height: 1px; background: var(--border); }

/* FIELD GRID */
.fgrid { display: grid; gap: 6px; }
.fgrid.g2 { grid-template-columns: repeat(2, 1fr); }
.fgrid.g3 { grid-template-columns: repeat(3, 1fr); }
.fgrid.g4 { grid-template-columns: repeat(4, 1fr); }
.fgrid.g5 { grid-template-columns: repeat(5, 1fr); }
.field-row { display: flex; align-items: stretch; border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; min-height: 32px; }
.field-row.full { grid-column: 1 / -1; }
.field-row.span2 { grid-column: span 2; }
.field-row.span3 { grid-column: span 3; }
.fl { background: #F8FAF9; padding: 5px 10px; font-size: 10px; font-weight: 700; color: var(--muted); min-width: 110px; display: flex; align-items: center; border-right: 1px solid var(--border); flex-shrink: 0; text-transform: uppercase; letter-spacing: .04em; line-height: 1.3; }
.fl.w80 { min-width: 80px; }
.fl.w140 { min-width: 140px; }
.fv { background: #fff; padding: 5px 10px; font-size: 12px; color: var(--text); flex: 1; display: flex; align-items: center; outline: none; font-family: inherit; text-transform: capitalize; }
.fv:focus { background: var(--tint2); color: var(--dark); }
.fv.mono { font-family: 'DM Mono', monospace; font-size: 11px; text-transform: none; }
.fv.allcaps { text-transform: uppercase; }
.fv-dollar { text-transform: none; }

/* DATE INPUT inside field-row */
input.fv-date { background: #fff; border: none; outline: none; font-family: inherit; font-size: 12px; color: var(--text); flex: 1; padding: 5px 10px; width: 100%; cursor: text; }
input.fv-date:focus { background: var(--tint2); color: var(--dark); }
input.fv-date::placeholder { color: var(--muted); font-weight: 400; }

/* SELECT */
.fv-drop { background: #fff; flex: 1; display: flex; align-items: center; padding: 0; }
.fv-drop:focus-within { background: var(--tint2); }
.form-select { width: 100%; height: 100%; border: none; background: transparent; font-family: inherit; font-size: 12px; color: var(--text); outline: none; cursor: pointer; padding: 5px 10px; }
.form-select:focus { color: var(--dark); font-weight: 600; }
.form-select.has-value { background: var(--tint); color: var(--dark); font-weight: 600; }

/* YES/NO TOGGLE */
.yn-row { display: flex; align-items: center; border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; min-height: 32px; }
.yn-label { background: #F8FAF9; padding: 5px 10px; font-size: 10px; font-weight: 700; color: var(--muted); flex: 1; display: flex; align-items: center; border-right: 1px solid var(--border); text-transform: uppercase; letter-spacing: .04em; }
.yn-btns { display: flex; }
.yn-btn { padding: 5px 13px; font-size: 11px; font-weight: 600; color: #aaa; background: #fff; border-left: 1px solid var(--border); cursor: pointer; transition: background .12s, color .12s; user-select: none; }
.yn-btn:hover { background: var(--tint); color: var(--dark); }
.yn-btn.active { background: var(--green); color: #fff; font-weight: 700; border-color: var(--green); }

/* CONDITIONAL BOXES */
.cond-box { display: none; grid-column: 1 / -1; background: var(--warn-bg); border: 1px solid var(--warn-bd); border-left: 4px solid var(--warn); border-radius: var(--radius); padding: 14px 16px; margin-top: 4px; }
.cond-box.visible { display: block; animation: fadeSlide .25s; }
.cond-box h5 { font-size: 11px; font-weight: 700; color: var(--dark); margin-bottom: 10px; text-transform: uppercase; letter-spacing: .06em; }
@keyframes fadeSlide { from { opacity: 0; transform: translateY(-4px); } to { opacity: 1; transform: translateY(0); } }

/* SUB-COND (inside FAQ items) */
.sub-cond { display: none; margin-top: 8px; }
.sub-cond.visible { display: block; animation: fadeSlide .2s; }

/* PROCEDURES TABLE */
.table-wrap { border: 1px solid var(--border); border-radius: var(--radius); overflow: hidden; margin-bottom: 10px; }
.proc-table { width: 100%; border-collapse: collapse; font-size: 12px; }
.proc-table th { background: var(--tint2); color: var(--dark); font-size: 9px; font-weight: 700; text-transform: uppercase; letter-spacing: .08em; padding: 8px 10px; border-bottom: 2px solid var(--green); text-align: left; }
.proc-table td { border-bottom: 1px solid var(--border); vertical-align: middle; padding: 0; }
.proc-table tr:last-child td { border-bottom: none; }
.proc-table tr:nth-child(even) td { background: #FAFBFA; }
.code-cell { padding: 6px 10px; white-space: nowrap; }
.d-badge { display: inline-flex; align-items: center; background: var(--tint); border-radius: 4px; padding: 2px 6px; gap: 2px; }
.d-prefix { font-size: 11px; font-weight: 700; color: var(--green); font-family: 'DM Mono', monospace; }
.code-input { border: none; background: transparent; width: 44px; font-size: 11px; font-weight: 700; color: var(--text); font-family: 'DM Mono', monospace; outline: none; text-align: center; }
.code-input:focus { color: var(--dark); }
.proc-name { font-size: 11px; color: #555; padding: 6px 10px; }
.table-select { width: 100%; height: 100%; border: none; background: transparent; font-family: inherit; font-size: 11px; color: var(--text); cursor: pointer; outline: none; padding: 6px 8px; }
.table-select:focus { background: var(--tint2); color: var(--dark); font-weight: 600; }
.remove-btn { background: none; border: none; color: #ddd; cursor: pointer; font-size: 18px; line-height: 1; padding: 4px 10px; transition: color .12s; }
.remove-btn:hover { color: #EF4444; }
.btn-add { display: inline-flex; align-items: center; gap: 6px; background: var(--tint); color: var(--dark); border: 1px solid #B2D8C8; border-radius: var(--radius); padding: 8px 16px; font-family: inherit; font-size: 12px; font-weight: 700; cursor: pointer; transition: background .12s; }
.btn-add:hover { background: #C6EAD9; }

/* FAQ */
.faq-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; align-items: stretch; }
.faq-item { background: #FAFAFA; border: 1px solid var(--border); border-radius: var(--radius); padding: 12px 14px; display: flex; flex-direction: column; }
.faq-item.full { grid-column: 1 / -1; }
.faq-q { display: block; font-size: 11px; font-weight: 700; color: var(--dark); margin-bottom: 8px; }
.faq-note { margin-top: 8px; }
.faq-note .fv { font-size: 11px; }

/* DOLLAR FIELDS */
.field-row .dollar-prefix { background: #F8FAF9; padding: 5px 6px 5px 10px; font-size: 12px; font-weight: 700; color: var(--dark); border-right: none; display: flex; align-items: center; flex-shrink: 0; }
.field-row .fv-dollar { background: #fff; border: none; outline: none; font-family: inherit; font-size: 12px; color: var(--text); flex: 1; padding: 5px 10px 5px 2px; }
.field-row .fv-dollar:focus { background: var(--tint2); color: var(--dark); }


.notes-area { width: 100%; min-height: 80px; padding: 12px 14px; border: 1px solid var(--border); border-radius: var(--radius); background: #FAFAFA; color: var(--text); font-family: inherit; font-size: 13px; outline: none; resize: vertical; line-height: 1.6; }
.notes-area:focus { background: #fff; border-color: var(--green); }

/* ACTION BAR / FOOTER */
.action-bar { text-align: center; padding: 20px 28px; }
.footer { display: flex; align-items: center; justify-content: center; gap: 8px; padding: 14px 28px; border-top: 1px solid var(--border); font-size: 11px; color: var(--muted); }
.footer-dot { width: 22px; height: 22px; background: var(--green); border-radius: 50%; display: flex; align-items: center; justify-content: center; }
.footer-dot span { font-size: 8px; font-weight: 700; color: #fff; }

/* PRINT */
@page { size: auto; margin: 0; }
@media print {
  body { background: #fff; zoom: 80%; }
  .toolbar, .btn-add, .remove-btn, .action-bar { display: none !important; }
  .page { max-width: 100%; border: none; margin: 0; }
  .verified-input { background: transparent; border: none; color: #fff; }
  .cond-box { border: 1px solid var(--green); }
  select { -webkit-appearance: none; appearance: none; }
  .proc-table th, .header, .sec-num { -webkit-print-color-adjust: exact; print-color-adjust: exact; }
  .yn-btn.active { -webkit-print-color-adjust: exact; print-color-adjust: exact; }
  .form-select.has-value { -webkit-print-color-adjust: exact; print-color-adjust: exact; }
}
</style>
</head>
<body>
<div class="page">



  <!-- HEADER -->
  <div class="header">
    <div class="header-left">
      <div class="logo-circle"><span>GO</span></div>
      <div>
        <div class="header-title">Insurance Verification Form</div>
        <div class="header-sub">Electronic Benefits Summary · CDT 2026</div>
      </div>
    </div>
    <div class="verified-block">
      <span class="verified-label">Verified by</span>
      <input type="text" class="verified-input" placeholder="Your name…" id="verifiedBy" oninput="updateVerifiedName(this)">
    </div>
  </div>

  <!-- META STRIP -->
  <div class="meta-strip" style="grid-template-columns: repeat(4, 1fr);">
    <div class="meta-cell">
      <div class="meta-lbl">Date of Call</div>
      <input type="text" id="callDate" class="date-mask" placeholder="MM/DD/YYYY" maxlength="10" style="border:none;outline:none;font-family:inherit;font-size:12px;font-weight:500;color:var(--text);background:transparent;width:100%;">
    </div>
    <div class="meta-cell">
      <div class="meta-lbl">Carrier Name</div>
      <div class="meta-val allcaps" contenteditable="true" style="text-transform:uppercase;"></div>
    </div>
    <div class="meta-cell">
      <div class="meta-lbl">Insurance Phone</div>
      <input type="text" id="insurancePhone" class="phone-mask" placeholder="(XXX) XXX-XXXX" maxlength="14" style="border:none;outline:none;font-family:inherit;font-size:12px;font-weight:500;color:var(--text);background:transparent;width:100%;">
    </div>
    <div class="meta-cell">
      <div class="meta-lbl">Call Ref #</div>
      <div class="meta-val" contenteditable="true"></div>
    </div>
  </div>

  <!-- ══════════════════════════════════════════════
       SECTION 1 · PLAN & CARRIER INFO
  ══════════════════════════════════════════════ -->
  <div class="section">
    <div class="sec-header">
      <div class="sec-num">1</div>
      <span class="sec-title">Plan &amp; Carrier Info</span>
    </div>
    <div class="fgrid g3">
      <div class="field-row">
        <div class="fl">Group Plan Name</div>
        <div class="fv" contenteditable="true"></div>
      </div>
      <div class="field-row">
        <div class="fl">Group #</div>
        <div class="fv mono" contenteditable="true"></div>
      </div>
      <div class="field-row">
        <div class="fl">Payor ID</div>
        <div class="fv mono" contenteditable="true"></div>
      </div>
      <!-- Effective Date — real date picker (MM/DD/YYYY in US browsers) -->
      <div class="field-row">
        <div class="fl">Effective Date</div>
        <input type="text" class="fv-date date-mask" id="effectiveDate" placeholder="MM/DD/YYYY" maxlength="10">
      </div>
      <!-- Benefit Type — replaces old "Cal./Benefit Year" -->
      <div class="field-row">
        <div class="fl">Benefit Type</div>
        <div class="fv-drop">
          <select class="form-select" id="benefitType" onchange="toggleBenefitOther()">
            <option value="">Select…</option>
            <option>Calendar Year</option>
            <option>Fiscal Year</option>
            <option>Contract Year</option>
            <option>Policy Year</option>
            <option value="Other">Other</option>
          </select>
        </div>
      </div>
      <!-- "Other" benefit type text input -->
      <div class="cond-box" id="benefitOtherBox">
        <h5>Specify Benefit Type</h5>
        <div class="field-row" style="max-width:420px;">
          <div class="fl w80">Details</div>
          <div class="fv" contenteditable="true" placeholder="Describe benefit year type…"></div>
        </div>
      </div>

      <div class="field-row">
        <div class="fl">Network Status</div>
        <div class="fv-drop">
          <select class="form-select" id="networkStatus" onchange="toggleOON()">
            <option value="In">In-Network (PPO)</option>
            <option value="Out">Out-of-Network</option>
            <option value="HMO">HMO / DMO</option>
          </select>
        </div>
      </div>
      <div class="field-row full">
        <div class="fl w80">Claims Address</div>
        <div class="fv" contenteditable="true"></div>
      </div>

      <!-- OON Conditional -->
      <div class="cond-box" id="oonBox">
        <h5>⚠ Out-of-Network Details</h5>
        <div class="field-row" style="max-width:300px;">
          <div class="fl">OON Coverage?</div>
          <div class="fv-drop"><select class="form-select"><option value="">Select…</option><option>Yes</option><option>No</option></select></div>
        </div>
      </div>
    </div>
  </div>

  <!-- ══════════════════════════════════════════════
       SECTION 2 · SUBSCRIBER & PATIENT
  ══════════════════════════════════════════════ -->
  <div class="section">
    <div class="sec-header">
      <div class="sec-num">2</div>
      <span class="sec-title">Subscriber &amp; Patient</span>
    </div>
    <div class="fgrid g3" style="margin-bottom:8px;">
      <div class="field-row">
        <div class="fl">Subscriber Name</div>
        <div class="fv" id="subscriberName" contenteditable="true" oninput="updateDocTitle()"></div>
      </div>
      <div class="field-row">
        <div class="fl">Subscriber DOB</div>
        <input type="text" class="fv-date date-mask" id="subscriberDob" placeholder="MM/DD/YYYY" maxlength="10">
      </div>
      <div class="field-row">
        <div class="fl">Sub ID / SSN</div>
        <div class="fv mono" contenteditable="true" style="text-transform:uppercase;"></div>
      </div>
    </div>
    <div class="fgrid g3">
      <div class="field-row">
        <div class="fl">Patient Name</div>
        <div class="fv" id="patientName" contenteditable="true" oninput="updateDocTitle()"></div>
      </div>
      <div class="field-row">
        <div class="fl">Patient DOB</div>
        <input type="text" class="fv-date date-mask" id="patientDob" placeholder="MM/DD/YYYY" maxlength="10">
      </div>
      <div class="field-row">
        <div class="fl">Relationship</div>
        <div class="fv-drop"><select class="form-select" id="relationship" onchange="updateDocTitle()">
          <option value="">Select…</option>
          <option>Self</option><option>Spouse</option><option>Child</option><option>Other</option>
        </select></div>
      </div>
    </div>
  </div>

  <!-- ══════════════════════════════════════════════
       SECTION 3 · BENEFITS & MAXIMUMS
  ══════════════════════════════════════════════ -->
  <div class="section">
    <div class="sec-header">
      <div class="sec-num">3</div>
      <span class="sec-title">Benefits &amp; Maximums</span>
    </div>
    <div class="fgrid g2" style="margin-bottom:6px;">
      <div class="field-row">
        <div class="fl w80">Annual Max</div>
        <span class="dollar-prefix">$</span><input class="fv-dollar" type="text" placeholder="0.00">
      </div>
      <div class="field-row">
        <div class="fl w80">Max Remaining</div>
        <span class="dollar-prefix">$</span><input class="fv-dollar" type="text" placeholder="0.00">
      </div>
    </div>
    <div class="fgrid g2" style="margin-bottom:6px;">
      <div class="field-row">
        <div class="fl w80">Indiv. Ded.</div>
        <span class="dollar-prefix">$</span><input class="fv-dollar" type="text" placeholder="0.00">
      </div>
      <div class="field-row">
        <div class="fl w80">Indiv. Ded. Rem.</div>
        <span class="dollar-prefix">$</span><input class="fv-dollar" type="text" placeholder="0.00">
      </div>
    </div>
    <div class="fgrid g2">
      <div class="field-row">
        <div class="fl w80">Family Ded.</div>
        <span class="dollar-prefix">$</span><input class="fv-dollar" type="text" placeholder="0.00">
      </div>
      <div class="field-row">
        <div class="fl w80">Family Ded. Rem.</div>
        <span class="dollar-prefix">$</span><input class="fv-dollar" type="text" placeholder="0.00">
      </div>
    </div>
  </div>

  <!-- ══════════════════════════════════════════════
       SECTION 4 · COVERAGE PERCENTAGES
  ══════════════════════════════════════════════ -->
  <div class="section">
    <div class="sec-header">
      <div class="sec-num">4</div>
      <span class="sec-title">Coverage Percentages</span>
    </div>

    <!-- Row 1: Preventive / Basic / Major / Ortho toggle -->
    <div class="fgrid g4" style="margin-bottom:8px;">
      <div class="field-row">
        <div class="fl w80">Preventive %</div>
        <input class="fv-dollar pct-input" type="text" placeholder="0" maxlength="3" style="text-align:center;flex:1;">
        <span class="pct-live" style="padding:5px 8px;font-size:12px;font-weight:700;color:var(--dark);background:#F8FAF9;border-left:1px solid var(--border);display:flex;align-items:center;min-width:28px;"></span>
      </div>
      <div class="field-row">
        <div class="fl w80">Basic %</div>
        <input class="fv-dollar pct-input" type="text" placeholder="0" maxlength="3" style="text-align:center;flex:1;">
        <span class="pct-live" style="padding:5px 8px;font-size:12px;font-weight:700;color:var(--dark);background:#F8FAF9;border-left:1px solid var(--border);display:flex;align-items:center;min-width:28px;"></span>
      </div>
      <div class="field-row">
        <div class="fl w80">Major %</div>
        <input class="fv-dollar pct-input" type="text" placeholder="0" maxlength="3" style="text-align:center;flex:1;">
        <span class="pct-live" style="padding:5px 8px;font-size:12px;font-weight:700;color:var(--dark);background:#F8FAF9;border-left:1px solid var(--border);display:flex;align-items:center;min-width:28px;"></span>
      </div>
      <div class="yn-row">
        <div class="yn-label">Ortho?</div>
        <div class="yn-btns" id="orthoToggle">
          <div class="yn-btn">Yes</div>
          <div class="yn-btn">No</div>
        </div>
      </div>
    </div>

    <!-- Ortho sub-fields -->
    <div class="cond-box" id="orthoBox" style="margin-bottom:8px;">
      <h5>Ortho Benefits</h5>
      <!-- Row 1: Ortho % | Lifetime Max? | Ded. Applies? -->
      <div class="fgrid g3" style="margin-bottom:6px;">
        <div class="field-row">
          <div class="fl w80">Ortho %</div>
          <input class="fv-dollar pct-input" type="text" placeholder="0" maxlength="3" style="text-align:center;flex:1;">
          <span class="pct-live" style="padding:5px 8px;font-size:12px;font-weight:700;color:var(--dark);background:#F8FAF9;border-left:1px solid var(--border);display:flex;align-items:center;min-width:28px;"></span>
        </div>
        <div class="yn-row">
          <div class="yn-label">Lifetime Max?</div>
          <div class="yn-btns" id="orthoLifetimeToggle">
            <div class="yn-btn">Yes</div>
            <div class="yn-btn">No</div>
          </div>
        </div>
        <div class="yn-row">
          <div class="yn-label">Ded. Applies?</div>
          <div class="yn-btns" id="orthoDedToggle">
            <div class="yn-btn">Yes</div>
            <div class="yn-btn">No</div>
          </div>
        </div>
      </div>
      <!-- Row 2: Annual Max | Remaining | (Ded. Amount if applies) | (Ded. Remaining if applies) — centered -->
      <div class="fgrid g2" style="max-width:60%;margin:0 auto 6px;">
        <div class="field-row">
          <div class="fl w80" id="orthoMaxLabel">Annual Max</div>
          <span class="dollar-prefix">$</span><input class="fv-dollar" type="text" placeholder="0.00">
        </div>
        <div class="field-row">
          <div class="fl w80">Remaining</div>
          <span class="dollar-prefix">$</span><input class="fv-dollar" type="text" placeholder="0.00">
        </div>
      </div>
      <!-- Ded sub-boxes: shown under annual max row when Ded. Applies = Yes -->
      <div class="cond-box" id="orthoDedBox" style="margin-bottom:6px;">
        <div class="fgrid g2" style="max-width:60%;margin:0 auto;">
          <div class="field-row">
            <div class="fl w80">Ded. Amount</div>
            <span class="dollar-prefix">$</span><input class="fv-dollar" type="text" placeholder="0.00">
          </div>
          <div class="field-row">
            <div class="fl w80">Ded. Remaining</div>
            <span class="dollar-prefix">$</span><input class="fv-dollar" type="text" placeholder="0.00">
          </div>
        </div>
      </div>
      <!-- Row 3: Child Age Limit | Emplo. Age Limit — centered -->
      <div class="fgrid g2" style="max-width:60%;margin:0 auto;">
        <div class="field-row">
          <div class="fl w80">Child Age Limit</div>
          <div class="fv" contenteditable="true" style="text-transform:none;text-align:center;justify-content:center;" placeholder="–"></div>
        </div>
        <div class="field-row">
          <div class="fl w80">Emplo. Age Limit</div>
          <div class="fv" contenteditable="true" style="text-transform:none;text-align:center;justify-content:center;" placeholder="–"></div>
        </div>
      </div>
    </div>

    <!-- Row 2: Category selectors -->
    <div class="fgrid g4" style="margin-bottom:8px;">
      <div class="field-row">
        <div class="fl w80">Endo</div>
        <div class="fv-drop"><select class="form-select">
          <option value="">Category…</option><option>Basic</option><option>Major</option><option>Preventive</option><option>Not Covered</option>
        </select></div>
      </div>
      <div class="field-row">
        <div class="fl w80">Perio</div>
        <div class="fv-drop"><select class="form-select">
          <option value="">Category…</option><option>Basic</option><option>Major</option><option>Preventive</option><option>Not Covered</option>
        </select></div>
      </div>
      <div class="field-row">
        <div class="fl w80">Simple Ext.</div>
        <div class="fv-drop"><select class="form-select">
          <option value="">Category…</option><option>Basic</option><option>Major</option><option>Not Covered</option>
        </select></div>
      </div>
      <div class="field-row">
        <div class="fl w80">Surgical Ext.</div>
        <div class="fv-drop"><select class="form-select">
          <option value="">Category…</option><option>Basic</option><option>Major</option><option>Not Covered</option>
        </select></div>
      </div>
    </div>

    <!-- Row 3: Toggle rows -->
    <div class="fgrid g3" style="margin-bottom:6px;">
      <!-- Deductible applies — multi-select category buttons -->
      <div class="yn-row">
        <div class="yn-label">Ded. Category</div>
        <div class="yn-btns" id="dedCatToggle">
          <div class="yn-btn">Preventive</div>
          <div class="yn-btn">Basic</div>
          <div class="yn-btn">Major</div>
        </div>
      </div>
      <div class="yn-row">
        <div class="yn-label">Diag App. Max</div>
        <div class="yn-btns"><div class="yn-btn">Yes</div><div class="yn-btn">No</div></div>
      </div>
      <!-- Waiting Period -->
      <div class="yn-row">
        <div class="yn-label">Waiting Period?</div>
        <div class="yn-btns" id="waitToggle">
          <div class="yn-btn">Yes</div>
          <div class="yn-btn">No</div>
        </div>
      </div>
    </div>

    <!-- Waiting Period conditional box -->
    <div class="fgrid g1">
      <div class="cond-box" id="waitBox">
        <h5>⚠ Waiting Period Details</h5>
        <div class="fgrid g4">
          <div class="field-row">
            <div class="fl w80">Preventive</div>
            <input class="fv-dollar" type="number" min="0" max="60" placeholder="0" id="waitPrev" style="width:40px;text-align:center;">
            <span class="dollar-prefix" style="border-left:1px solid var(--border);border-right:none;font-size:10px;letter-spacing:.04em;">MONTHS</span>
          </div>
          <div class="field-row">
            <div class="fl w80">Basic</div>
            <input class="fv-dollar" type="number" min="0" max="60" placeholder="0" id="waitBasic" style="width:40px;text-align:center;">
            <span class="dollar-prefix" style="border-left:1px solid var(--border);border-right:none;font-size:10px;letter-spacing:.04em;">MONTHS</span>
          </div>
          <div class="field-row">
            <div class="fl w80">Major</div>
            <input class="fv-dollar" type="number" min="0" max="60" placeholder="0" id="waitMajor" style="width:40px;text-align:center;">
            <span class="dollar-prefix" style="border-left:1px solid var(--border);border-right:none;font-size:10px;letter-spacing:.04em;">MONTHS</span>
          </div>
          <div class="field-row">
            <div class="fl w80">Ortho</div>
            <input class="fv-dollar" type="number" min="0" max="60" placeholder="0" id="waitOrtho" style="width:40px;text-align:center;">
            <span class="dollar-prefix" style="border-left:1px solid var(--border);border-right:none;font-size:10px;letter-spacing:.04em;">MONTHS</span>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- ══════════════════════════════════════════════
       SECTION 4.5 · APPT CODES
  ══════════════════════════════════════════════ -->
  <div class="section">
    <div class="sec-header">
      <div class="sec-num">★</div>
      <span class="sec-title">Appt Codes</span>
    </div>
    <div id="apptCodesWrap" style="display:none; margin-bottom:10px;">
      <div class="table-wrap">
        <table class="proc-table">
          <thead>
            <tr>
              <th style="width:110px;">CDT Code</th>
              <th>Description</th>
              <th style="width:80px;">Benefit %</th>
              <th style="width:200px;">Frequency</th>
              <th style="width:80px;">Ded Applies?</th>
              <th style="width:80px;">Age Limit</th>
              <th style="width:36px;"></th>
            </tr>
          </thead>
          <tbody id="apptBody"></tbody>
        </table>
      </div>
      <button class="btn-add" onclick="addApptRow()" style="margin-bottom:10px;">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
        Add Code
      </button>
      <textarea class="notes-area" placeholder="Appt codes notes…" style="min-height:60px;"></textarea>
    </div>
    <button class="btn-add" id="apptToggleBtn" onclick="toggleApptCodes(this)">
      <svg id="apptToggleIcon" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
      <span id="apptToggleLabel">Add Appt Codes</span>
    </button>
  </div>

  <!-- ══════════════════════════════════════════════
       SECTION 5 · PROCEDURES (CDT 2026)
  ══════════════════════════════════════════════ -->
  <div class="section">
    <div class="sec-header">
      <div class="sec-num">5</div>
      <span class="sec-title">Common Procedures · CDT 2026</span>
    </div>
    <div class="table-wrap">
      <table class="proc-table">
        <thead>
          <tr>
            <th style="width:110px;">CDT Code</th>
            <th>Description</th>
            <th style="width:80px;">Benefit %</th>
            <th style="width:200px;">Frequency</th>
            <th style="width:80px;">Ded Applies?</th>
            <th style="width:80px;">Age Limit</th>
            <th style="width:36px;"></th>
          </tr>
        </thead>
        <tbody id="procBody"></tbody>
      </table>
    </div>
    <button class="btn-add" onclick="addProcRow()">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
      Add Procedure Row
    </button>
  </div>

  <!-- ══════════════════════════════════════════════
       SECTION 6 · POLICY RULES
  ══════════════════════════════════════════════ -->
  <div class="section">
    <div class="sec-header">
      <div class="sec-num">6</div>
      <span class="sec-title">Policy Rules</span>
    </div>
    <div class="faq-grid">

      <!-- 1. Posterior composites downgraded? -->
      <div class="faq-item">
        <span class="faq-q">Are posterior composites downgraded?</span>
        <div class="yn-row" style="margin-top:0;margin-bottom:6px;">
          <div class="yn-btns" style="width:100%;">
            <div class="yn-btn" style="border-left:none;">Yes</div>
            <div class="yn-btn">No</div>
          </div>
        </div>
        <div class="field-row faq-note">
          <div class="fl w80">Notes</div>
          <div class="fv" contenteditable="true"></div>
        </div>
      </div>

      <!-- 2. Prep vs Seat date -->
      <div class="faq-item">
        <span class="faq-q">Does the carrier pay on the prep date or the seat date?</span>
        <div class="yn-row" style="margin-top:0;margin-bottom:6px;">
          <div class="yn-btns" style="width:100%;">
            <div class="yn-btn" style="border-left:none;">Prep Date</div>
            <div class="yn-btn">Seat Date</div>
          </div>
        </div>
        <div class="field-row faq-note">
          <div class="fl w80">Notes</div>
          <div class="fv" contenteditable="true"></div>
        </div>
      </div>

      <!-- 3. Can all 4 quads be done on the same day? -->
      <div class="faq-item">
        <span class="faq-q">Can all 4 quads be done on the same day?</span>
        <div class="yn-row" style="margin-top:0;margin-bottom:6px;">
          <div class="yn-btns" style="width:100%;">
            <div class="yn-btn" style="border-left:none;">2</div>
            <div class="yn-btn">4</div>
          </div>
        </div>
        <div class="field-row faq-note">
          <div class="fl w80">Notes</div>
          <div class="fv" contenteditable="true"></div>
        </div>
      </div>

      <!-- 4. Can quads be done same day as prophy? -->
      <div class="faq-item">
        <span class="faq-q">Can quads be done on the same day as prophy?</span>
        <div class="yn-row" style="margin-top:0;margin-bottom:6px;">
          <div class="yn-btns" style="width:100%;">
            <div class="yn-btn" style="border-left:none;">Yes</div>
            <div class="yn-btn">No</div>
          </div>
        </div>
        <div class="field-row faq-note">
          <div class="fl w80">Notes</div>
          <div class="fv" contenteditable="true"></div>
        </div>
      </div>

      <!-- 5. Periodontal shares frequency with prophy? -->
      <div class="faq-item">
        <span class="faq-q">Periodontal shares frequency with prophy?</span>
        <div class="yn-row" style="margin-top:0;margin-bottom:6px;">
          <div class="yn-btns" id="perioFreqToggle" style="width:100%;">
            <div class="yn-btn" style="border-left:none;">Yes</div>
            <div class="yn-btn">No</div>
          </div>
        </div>
        <div class="sub-cond" id="perioFreqSub">
          <div class="fgrid g3" style="margin-bottom:6px;gap:4px;">
            <div class="yn-row" style="min-height:26px;">
              <div class="yn-label" style="font-size:9px;padding:3px 7px;">D4346?</div>
              <div class="yn-btns">
                <div class="yn-btn" style="border-left:none;padding:3px 9px;font-size:10px;">Yes</div>
                <div class="yn-btn" style="padding:3px 9px;font-size:10px;">No</div>
              </div>
            </div>
            <div class="yn-row" style="min-height:26px;">
              <div class="yn-label" style="font-size:9px;padding:3px 7px;">D4355?</div>
              <div class="yn-btns">
                <div class="yn-btn" style="border-left:none;padding:3px 9px;font-size:10px;">Yes</div>
                <div class="yn-btn" style="padding:3px 9px;font-size:10px;">No</div>
              </div>
            </div>
            <div class="yn-row" style="min-height:26px;">
              <div class="yn-label" style="font-size:9px;padding:3px 7px;">D4910?</div>
              <div class="yn-btns">
                <div class="yn-btn" style="border-left:none;padding:3px 9px;font-size:10px;">Yes</div>
                <div class="yn-btn" style="padding:3px 9px;font-size:10px;">No</div>
              </div>
            </div>
          </div>
        </div>
        <div class="field-row faq-note">
          <div class="fl w80">Notes</div>
          <div class="fv" contenteditable="true"></div>
        </div>
      </div>

      <!-- 6. Missing Tooth Clause? -->
      <div class="faq-item">
        <span class="faq-q">Missing Tooth Clause?</span>
        <div class="yn-row" style="margin-top:0;margin-bottom:6px;">
          <div class="yn-btns" style="width:100%;">
            <div class="yn-btn" style="border-left:none;">Yes</div>
            <div class="yn-btn">No</div>
          </div>
        </div>
        <div class="field-row faq-note">
          <div class="fl w80">Notes</div>
          <div class="fv" contenteditable="true"></div>
        </div>
      </div>

      <!-- 7. Perio maintenance same day as exam? -->
      <div class="faq-item">
        <span class="faq-q">Perio maintenance — same day as exam?</span>
        <div class="yn-row" style="margin-top:0;margin-bottom:6px;">
          <div class="yn-btns" style="width:100%;">
            <div class="yn-btn" style="border-left:none;">Yes</div>
            <div class="yn-btn">No</div>
          </div>
        </div>
        <div class="field-row faq-note">
          <div class="fl w80">Notes</div>
          <div class="fv" contenteditable="true"></div>
        </div>
      </div>

      <!-- 8. Implant exclusions? -->
      <div class="faq-item">
        <span class="faq-q">Implant coverage — any exclusions?</span>
        <div class="yn-row" style="margin-top:0;margin-bottom:6px;">
          <div class="yn-btns" style="width:100%;">
            <div class="yn-btn" style="border-left:none;">Yes</div>
            <div class="yn-btn">No</div>
          </div>
        </div>
        <div class="field-row faq-note">
          <div class="fl w80">Notes</div>
          <div class="fv" contenteditable="true"></div>
        </div>
      </div>

      <!-- 9. Occ. Guards covered? -->
      <div class="faq-item">
        <span class="faq-q">Occ. Guards covered?</span>
        <div class="yn-row" style="margin-top:0;margin-bottom:6px;">
          <div class="yn-btns" id="occGuardToggle" style="width:100%;">
            <div class="yn-btn" style="border-left:none;">Yes</div>
            <div class="yn-btn">No</div>
          </div>
        </div>
        <div class="sub-cond" id="occGuardSub">
          <span class="faq-q" style="margin-top:4px;margin-bottom:6px;display:block;">For bruxism only?</span>
          <div class="yn-row" style="margin-bottom:6px;">
            <div class="yn-btns" style="width:100%;">
              <div class="yn-btn" style="border-left:none;">Yes</div>
              <div class="yn-btn">No</div>
            </div>
          </div>
        </div>
        <div class="field-row faq-note">
          <div class="fl w80">Notes</div>
          <div class="fv" contenteditable="true"></div>
        </div>
      </div>

      <!-- 10. Anesthesia regulation? -->
      <div class="faq-item">
        <span class="faq-q">Is there any regulation for anesthesia to be covered?</span>
        <div class="yn-row" style="margin-top:0;margin-bottom:6px;">
          <div class="yn-btns" id="anesToggle" style="width:100%;">
            <div class="yn-btn" style="border-left:none;">Yes</div>
            <div class="yn-btn">No</div>
          </div>
        </div>
        <div class="field-row faq-note">
          <div class="fl w80">Notes</div>
          <div class="fv" contenteditable="true"></div>
        </div>
      </div>

    </div>
  </div>

  <!-- GENERAL NOTES -->
  <div class="section">
    <div class="sec-header">
      <div class="sec-num" style="background:var(--muted);">✎</div>
      <span class="sec-title">General Notes</span>
    </div>
    <textarea class="notes-area" placeholder="Enter any extra details, call reference numbers, or special instructions…"></textarea>
  </div>

  <!-- ACTION BAR -->
  <div class="action-bar">
    <button class="print-btn" onclick="window.print()" style="padding:12px 28px;font-size:13px;">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 6 2 18 2 18 9"/><path d="M6 18H4a2 2 0 0 1-2-2v-5a2 2 0 0 1 2-2h16a2 2 0 0 1 2 2v5a2 2 0 0 1-2 2h-2"/><rect x="6" y="14" width="12" height="8"/></svg>
      Save as PDF / Print Form
    </button>
  </div>

  <!-- FOOTER -->
  <div class="footer" style="flex-direction:column;gap:4px;padding:16px 28px;">
    <div style="display:flex;align-items:center;gap:8px;">
      <div class="footer-dot"><span>GO</span></div>
      <span>GO Dental Brands · Insurance Verification · CDT 2026</span>
    </div>
    <div style="font-size:10px;color:var(--muted);text-align:center;">
      © <span id="footerYear"></span> GO Dental Brands. All rights reserved.
    </div>
    <div style="font-size:10px;color:var(--muted);text-align:center;letter-spacing:.02em;">
      By Guilherme Cruz &amp; Beatriz Maciel
    </div>
  </div>

</div><!-- /page -->

<script>
// ─── FULL CDT 2026 DATABASE ───────────────────────────────
// ─── DENTICON CDT DATABASE ───────────────────────────────
const CDT = {
  "0120":"Periodic Oral Evaluation","0126":"Examination - Periodic Denture",
  "0140":"Limited Oral Eval Prob Focused","0145":"Oral Eval Pt Under 3 Yrs, Counsel Primary",
  "0150":"Compsve Oral Eval - New/Est Pat","0160":"Detailed & Ext Oral Eval By Rp",
  "0170":"Re-Evaluation - Limited","0171":"Re-Evaluation - Post-Operative Office Visit",
  "0180":"Compsve Perio Eval New/Est Pat","0190":"Screening Of A Patient","0191":"Assessment Of A Patient",
  "0351":"3D Photographic Image","0391":"Interpretation Diag Image By Practitioner",
  "0393":"Treatment Simulation Using 3D Image Volume","0394":"Digital Subtraction Of Two+ Images",
  "0395":"Fusion Of 2 Or More 3D Image Volumes",
  "0411":"HbA1c In-Office Point Of Service Testing","0412":"Blood Glucose Level Test In-Office",
  "0414":"Laboratory Processing Of Microbial Specimen","0415":"Collection Of Microorganisms For Culture",
  "0416":"Viral Culture","0417":"Collection/Prep Of Saliva Sample",
  "0418":"Analysis Of Saliva Sample","0422":"Collection/Prep Of Genetic Sample Material",
  "0423":"Genetic Test For Susceptibility To Disease","0425":"Caries Susceptibility Tests",
  "0431":"Adjunctive Pre-diagnostic Test","0460":"Pulp Vitality Tests","0470":"Diagnostic Casts",
  "0472":"Accession - Gross","0473":"Accession - Gross/Micro","0474":"Accession - Gross W/Margins",
  "0475":"Decalcification Procedure","0476":"Special Stains For Microorganisms",
  "0477":"Special Stains, Not For Microorganisms","0478":"Immunohistochemical Stains",
  "0479":"Tissue In-situ Hybridization","0480":"Cytologic Smears","0481":"Electron Microscopy",
  "0482":"Direct Immunofluorescence","0483":"Indirect Immunofluorescence",
  "0484":"Consultation On Slides","0485":"Consultation, Including Prep",
  "0486":"Accession Of Transepithelial Cytologic Sample","0502":"Other Oral Path By Rp",
  "0600":"Non-Ionizing Diagnostic Procedure","0601":"Caries Risk Assessment - Low Risk",
  "0602":"Caries Risk Assessment - Moderate Risk","0603":"Caries Risk Assessment - High Risk",
  "0604":"Antigen Testing For Public Health Pathogen Incl COVID","0605":"Antibody Testing For Pathogens Inc COVID",
  "0701":"Panoramic Radiographic Image - Image Capture Only","0702":"2D Cephalometric Radiographic Img - Image Cap Only",
  "0704":"3D Photographic Image - Image Capture Only","0706":"Intraoral-Occlusal Radiographic Image - Img Capt Only",
  "0707":"Intraoral-Periapical Radiograph - Image Capt Only","0999":"Unspecified Diagnostic Procedure, By Report",
  "0210":"Intraoral - Complete Series Of Radiographic Images","0240":"Intraoral - Occlusal Radiographic Image",
  "0250":"Extra-oral - 2D Projection Radiographic Images","0251":"Extra-Oral Posterior Dental Radiographic Image",
  "0310":"Sialography","0320":"TMJ Arthrogram W/Injection","0321":"Other TMJ Radiographic Images, By Rpt",
  "0322":"Tomographic Survey","0330":"Panoramic Radiographic Image","0340":"2D Cephalometric Radiographic Image",
  "0350":"2D Oral/Facial Photographic Image",
  "0369":"Maxillofacial MRI Capture/Interpretation","0370":"Maxillofacial Ultrasound Capture/Interpretation",
  "0371":"Sialoendoscopy Capture/Interpretation","0385":"Maxillofacial MRI Image Capture",
  "0386":"Maxillofacial Ultrasound Image Capture",
  "0220":"Intraoral - Periapical First Radiographic Image","0230":"Intraoral - Periapical Each Addl Radiographic Image",
  "0270":"Bitewing - Single","0272":"Bitewings - Two Radiographic Images",
  "0273":"Bitewings - Three Radiographic Images","0274":"Bitewings - Four Radiographic Images",
  "0277":"Vertical Bitewings - 7-8 Radiographic Images",
  "0360":"Cone Beam CT Craniofacial Data Capture","0363":"Cone Beam 3D Image Reconstruction",
  "0364":"Cone Beam CT Limited View - Less Than Whole Jaw","0365":"Cone Beam CT Full Arch View - Mandible",
  "0366":"Cone Beam CT Full Arch View - Maxilla","0367":"Cone Beam CT Full 2 Jaw View",
  "0368":"Cone Beam CT For TMJ Series","0380":"Cone Beam CT Lmtd View Capture",
  "0381":"Cone Beam CT Capture Full Arch View - Mandible","0382":"Cone Beam CT Capture Full Arch View - Maxilla",
  "0383":"Cone Beam CT Capture Full 2 Jaw View","0384":"Cone Beam CT Capture TMJ Series",
  "1111":"Prophylaxis - Adult (1 Visit)","1114":"Prophylaxis - Under 10 Teeth",
  "1116":"Prophylaxis - Denture Or Implant","1110":"Prophylaxis - Adult","1120":"Prophylaxis - Child",
  "1201":"Topical AP Of Fluoride (Inc Prophy) - Child","1203":"Topical AP Of Fluoride (Ex Prophy) - Child",
  "1204":"Topical AP Of Fluoride (Ex Prophy) Adult","1206":"Topical Application Of Fluoride Varnish",
  "1208":"Topical Application Of Fluoride - Excluding Varnish","1310":"Nutritional Counseling",
  "1320":"Tobacco Counsel For Oral Disease","1330":"Oral Hygiene Instructions",
  "1351":"Sealant - Per Tooth","1352":"Prev Resin Restoration In Mod-High Caries Pt",
  "1353":"Sealant Repair - Per Tooth","1354":"Interim Caries Arresting Medicament Application - Per Tooth",
  "1515":"Space Maintainer - Bilateral","1550":"Recement Or Rebond Space Maintainer",
  "1551":"Re-cement Bilateral Space Maintainer - Maxillary","1552":"Re-cement Bilateral Space Maintainer - Mandibular",
  "1553":"Re-cement Unilateral Space Maintainer - Per Quad","1555":"Removal Of Fixed Space Maintainer",
  "1557":"Removal Of Fixed Bilateral Space Maintainer - Max","1558":"Removal Of Fixed Bilateral Space Maintainer - Mand",
  "1999":"Unspecified Preventive Procedure, By Report",
  "1510":"Space Maintainer - Fixed - Unilateral","1516":"Space Maintainer - Fixed - Bilateral, Maxillary",
  "1517":"Space Maintainer - Fixed - Bilateral, Mandibular","1520":"Space Maintainer - Removable - Unilateral",
  "1526":"Space Maintainer - Removable - Bilateral, Maxillary","1527":"Space Maintainer - Removable - Bilateral, Mandibular",
  "1556":"Removal Of Fixed Unilateral Space Maintainer - Quad","1575":"Distal Shoe Space Maintainer - Fixed - Unilateral",
  "2140":"Amalgam One Surface","2150":"Amalgam Two Surface","2160":"Amalgam Three Surfaces","2161":"Amalgam Four/More Surfaces",
  "2330":"Resin Composite One Surface Anterior","2331":"Resin Composite Two Surfaces Anterior",
  "2332":"Resin Composite Three Surfaces Anterior","2335":"Resin Composite Four/More Surf Anterior",
  "2390":"Resin Composite Crown Anterior","2391":"Resin Composite One Surface Posterior",
  "2392":"Resin Composite Two Surfaces Posterior","2393":"Resin Composite Three Surfaces Posterior",
  "2394":"Resin Composite Four/More Surfaces Posterior",
  "2910":"Recement Or Rebond Inlay/Onlay/Veneer","2915":"Recement Or Rebond Indirect Fab Or Prefab Post/Cor",
  "2920":"Recement Or Rebond Crown","2921":"Reattachment Of Tooth Fragment, Incisal Edge/Cusp",
  "2928":"Prefabricated Porcelain/Ceramic Crown - Perm Tooth","2940":"Protective Restoration",
  "2941":"Interim Therapeutic Restoration - Primary Dentition","2949":"Restorative Foundation For An Indirect Restoration",
  "2951":"Pin Retention Per Tooth","2953":"Each Added Post, Indirect Fab - Same Tooth","2955":"Post Removal",
  "2957":"Each Added Prefab Post Same Tooth","2960":"Labial Veneer Resin Laminate Chair",
  "2961":"Labial Veneer Resin Laminate Lab","2962":"Labial Veneer Porcelain Laminate Lab",
  "2971":"Additional Procedures New Crown","2975":"Coping",
  "2981":"Inlay Repair - Restorative Material Failure","2982":"Onlay Repair - Restorative Material Failure",
  "2983":"Veneer Repair - Restorative Material Failure","2990":"Resin Infiltration Incipient Smooth Surface Lesion",
  "2999":"Unspecified Restorative Procedure, By Report",
  "2410":"Gold Foil - One Surface","2420":"Gold Foil - Two Surfaces","2430":"Gold Foil - Three Surfaces",
  "2510":"Inlay Metallic One Surface","2520":"Inlay Metallic Two Surfaces","2530":"Inlay Metallic Three Or More Surfaces",
  "2542":"Onlay Metallic Two Surfaces","2543":"Onlay Metallic Three Surface","2544":"Onlay Metallic Four Or More",
  "2610":"Inlay Porcelain/Ceramic One Surface","2620":"Inlay Porcelain/Ceramic Two Surfaces",
  "2630":"Inlay Porcelain/Ceramic Three+ Surfaces","2642":"Onlay Porcelain/Ceramic Two Surfaces",
  "2643":"Onlay Porcelain/Ceramic Three Surfaces","2644":"Onlay Porcelain/Ceramic Four+ Surfaces",
  "2650":"Inlay Composite/Resin One Surface","2651":"Inlay Composite/Resin Two Surfaces",
  "2652":"Inlay Comp/Resin Three+ Surfaces","2662":"Onlay Composite/Resin Two Surfaces",
  "2663":"Onlay Comp/Resin Three Surfaces","2664":"Onlay Comp/Resin Four+ Surfaces",
  "2710":"Crown - Resin Composite Indirect","2712":"Crown - 3/4 Resin-based Composite",
  "2720":"Crown Resin With High Noble Metal","2721":"Crown Resin W/ Predom Base Metal","2722":"Crown Resin W/ Noble Metal",
  "2740":"Crown Porcelain/Ceramic","2750":"Crown Porcelain Fused High Noble Metal",
  "2751":"Crown Porcelain Fused Base Metal","2752":"Crown Porcelain Fused Noble Metal",
  "2753":"Crown - Porcelain Fused To Titanium","2780":"Crown 3/4 Cast High Noble Metal",
  "2781":"Crown 3/4 Cast Pred Base Metal","2782":"Crown 3/4 Cast Noble Metal","2783":"Crown 3/4 Porcelain/Ceramic",
  "2790":"Crown Full Cast High Noble Metal","2791":"Crown Full Cast Base Predominantly Metal",
  "2792":"Crown Full Cast Noble Metal","2794":"Crown - Titanium","2799":"Provisional Crown",
  "2929":"Prefabricated Porcelain/Ceramic Crown - Primary","2930":"Prefabricated SS Crown Primary Tooth",
  "2931":"Prefabricated SS Crown Perm Tooth","2932":"Prefabricated Resin Crown",
  "2933":"Prefabricated SS Crown Resin Window","2934":"Prefabricated SS Crown - Esthetic Coat (Primary)",
  "2980":"Crown Repair - Restorative Material Failure",
  "2950":"Core Buildup, Including Any Pins When Required",
  "2952":"Post & Core (Addition To Crown), Indirect Fab","2954":"Prefab Post & Core (Addition To Crown)",
  "3110":"Pulp Cap Direct","3120":"Pulp Cap Indirect","3220":"Therapeutic Pulpotomy",
  "3221":"Pulpal Debridement Perm/Prim","3222":"Partial Pulpotomy, Apexogenesis",
  "3230":"Pulpal Therapy Anterior Primary","3240":"Pulpal Therapy Posterior Primary",
  "3310":"Endodontic Therapy, Anterior Tooth","3320":"Endodontic Therapy, Premolar Tooth",
  "3330":"Endodontic Therapy, Molar Tooth","3331":"Treatment Of Root Canal Obstruction",
  "3332":"Incomplete Endo Therapy Inoperable","3333":"Endo - Internal Root Repair",
  "3346":"Retreatment RCT/Anterior Endodontics","3347":"Retreatment Previous Root Canal Therapy - Premolar",
  "3348":"Retreatment RCT/Molar",
  "3351":"Apexification/Recalcification - Initial Visit","3352":"Apexification/Recalcification - Interim Medication",
  "3353":"Apexification/Recalcification (Final)","3355":"Pulpal Regeneration - Initial Visit",
  "3356":"Pulpal Regeneration - Interim Medication Replacement","3357":"Pulpal Regeneration - Completion Of Treatment",
  "3410":"Apicoectomy - Anterior","3421":"Apicoectomy - Premolar (First Root)",
  "3425":"Apicoectomy - Molar (First Root)","3426":"Apicoectomy - Each Additional Root",
  "3427":"Periradicular Surgery Without Apicoectomy",
  "3428":"Bone Graft W Periradicular Surgery - One Tooth","3429":"Bone Graft W Periradicular Surgery - Additional Tooth",
  "3430":"Retrograde Filling - Per Root","3431":"Biologic Materials - Aid Soft/Osseous Tissue W/Periradicular",
  "3432":"Guided Tissue Regeneration/Resorbable W/Periradicular","3450":"Root Amputation - Per Root",
  "3460":"Endo Endosseous Implant","3470":"Intentional Reimplantation",
  "3471":"Surgical Repair Of Root Resorption - Anterior","3472":"Surgical Repair Of Root Resorption - Premolar",
  "3473":"Surgical Repair Of Root Resorption - Molar","3910":"Surgical Procedure Isolation Tooth W/Rubber Dam",
  "3920":"Hemisection Not Including RCT","3950":"Canal Preparation - Performed Post",
  "3999":"Unspecified Endodontic Procedure, By Report",
  "4210":"Gingivectomy/Gingivoplasty 4+ Teeth Per Quad","4211":"Gingivectomy/Gingivoplasty 1-3 Teeth Per Quad",
  "4212":"Gingivectomy/Gingivoplasty For Restorative Proc, Per Tooth",
  "4230":"Anatomical Crown Exposure 4+ Teeth Per Quad","4231":"Anatomical Crown Exposure 1-3 Teeth Per Quad",
  "4240":"Gingival Flap W/Root Planing 4+ Teeth Per Quad","4241":"Gingival Flap W/Root Planing 1-3 Teeth Per Quad",
  "4245":"Apically Position Flap","4249":"Clinical Crown Lengthening Hard Tissue",
  "4260":"Osseous Surgery 4+ Teeth Per Quad","4261":"Osseous Surgery 1-3 Teeth Per Quad",
  "4263":"Bone Replacement Graft - Retained Natural Tooth, 1st","4264":"Bone Replacement Graft - Retained Natural Tooth, Additional",
  "4265":"Bio Materials Aid Tissue Regeneration","4266":"Guided Tissue Regen Resorbable",
  "4267":"Guided Tissue Regen Non-Resorbable","4268":"Surgical Revision Procedure Per Tooth",
  "4270":"Pedicle Soft Tissue Graft","4273":"Autogenous Connective Tissue Graft - 1st Tooth",
  "4274":"Mesial/Distal Wedge Procedure, Single Tooth","4275":"Non-Autogenous Connective Tissue Graft",
  "4276":"Connective Tissue & Double Pedicle Graft, Per Tooth",
  "4277":"Free Soft Tissue Graft - First Tooth In Graft","4278":"Free Soft Tissue Graft - Additional Tooth In Graft",
  "4283":"Autogenous Connective Tissue Graft - Each Contiguous Tooth",
  "4285":"Non-Autogenous Connective Tissue Graft - Each Contiguous Tooth",
  "4320":"Provisional Splinting Intracoronal","4321":"Provisional Splinting Extracoronal",
  "4322":"Splint - Intracoronal, Natural Teeth/Prosthetic Crown","4323":"Splint - Extracoronal; Natural Teeth/Prosthetic Crown",
  "4341":"Perio Scaling Root Planing 4+ Teeth Per Quad","4342":"Perio Scaling Root Planing 1-3 Teeth Per Quad",
  "4346":"Scaling Generalized Moderate/Severe Gingival Inflammation - Full Mouth",
  "4355":"Full Mouth Debridement - Subsequent Visit","4381":"Localized Delivery Antimicrobial Agents Controlled",
  "4382":"Arestin 2 Sites Per Tooth","4383":"Arestin 3 Sites Per Tooth",
  "4910":"Periodontal Maintenance","4920":"Unscheduled Dressing Change",
  "4921":"Gingival Irrigation - Per Quadrant","4999":"Unspecified Periodontic Procedure, By Report",
  "7110":"Extraction Single Tooth","7111":"Extraction, Coronal Remnants - Primary Tooth",
  "7140":"Extraction, Erupted Tooth Or Exposed Root","7210":"Extraction, Erupted Tooth Requiring Removal/Sectioning",
  "7220":"Removal Of Impacted Tooth - Soft Tissue","7230":"Removal Of Impacted Tooth - Partially Bony",
  "7240":"Removal Of Impacted Tooth - Completely Bony","7241":"Removal Impacted Tooth - Completely Bony W/Complications",
  "7250":"Removal Of Residual Tooth Roots","7251":"Coronectomy - Intentional Partial Tooth Removal",
  "7260":"Oroantral Fistula Closure","7261":"Primary Closure Of A Sinus Perforation",
  "7270":"Tooth Reimplant/Stabilization","7272":"Tooth Transplantation",
  "7280":"Exposure Of An Unerupted Tooth","7282":"Mobilization Of Erupted/Malpositioned Tooth",
  "7283":"Placement Of Device To Facilitate Eruption Of Impacted Tooth",
  "7285":"Incisional Biopsy Of Oral Tissue - Hard","7286":"Incisional Biopsy Of Oral Tissue - Soft",
  "7287":"Exfoliative Cytological Sample Collection","7288":"Brush Biopsy - Transepithelial Sample Collection",
  "7290":"Surgical Repositioning Of Teeth","7291":"Transseptal/Supra Crestal Fiberotomy",
  "7292":"Placement - Temporary Anchorage Device (Screw Retained Plate)",
  "7293":"Placement - Temporary Anchorage Device (Requiring Flap)","7294":"Placement - Temporary Anchorage Without Flap",
  "7295":"Harvest Of Bone Used In Autogenous Grafting","7296":"Corticotomy - 1-3 Teeth Per Quad",
  "7297":"Corticotomy - 4+ Teeth Per Quad","7298":"Removal Of Temporary Anchorage Device - Screw Retained",
  "7299":"Removal Of Temporary Anchorage Device, Requiring Flap",
  "7300":"Removal Of Temporary Anchorage Device, Without Flap",
  "7310":"Alveoplasty W Extractions 4+ Teeth Per Quad","7311":"Alveoplasty W Extractions - 1-3 Teeth Per Quad",
  "7320":"Alveoplasty Without Extraction - 4+ Teeth, Per Quad","7321":"Alveoplasty Without Extraction - 1-3 Teeth, Per Quad",
  "7340":"Vestibuloplasty - Ridge Extension (Secondary Epithelization)",
  "7350":"Vestibuloplasty - Ridge Extension",
  "7410":"Excision Of Benign Lesion Up To 1.25cm","7411":"Excision Of Benign Lesion Greater Than 1.25cm",
  "7412":"Excision Of Benign Lesion, Complicated","7413":"Excision Of Malignant Lesion Up To 1.25cm",
  "7414":"Excision Of Malignant Lesion Greater Than 1.25cm","7415":"Excision Of Malignant Lesion, Complicated",
  "7440":"Excision Of Malignant Tumor Up To 1.25cm","7441":"Excision Of Malignant Tumor > 1.25cm",
  "7450":"Remove Benign Odontogenic Cyst/Tumor < 1.25cm","7451":"Remove Benign Odontogenic Cyst/Tumor > 1.25cm",
  "7460":"Remove Benign Nonodontogenic Cyst/Tumor < 1.25cm","7461":"Remove Benign Nonodontogenic Cyst/Tumor > 1.25cm",
  "7465":"Destruction Of Lesions By Physical/Chemical","7471":"Removal Of Lateral Exostosis",
  "7472":"Removal Of Torus Palatinus","7473":"Removal Of Torus Mandibularis","7485":"Reduction Of Osseous Tuberosity",
  "7510":"I&D Of Abscess - Intraoral Soft Tissue","7511":"I&D Of Abscess - Intraoral Soft Tissue, Complicated",
  "7520":"I&D Of Abscess - Extraoral Soft Tissue","7521":"I&D Of Abscess - Extraoral Soft Tissue, Complicated",
  "7530":"Removal Foreign Body - Mucosa/Skin/Subcutaneous Alveolar",
  "7540":"Removal Reaction Producing Foreign Bodies","7550":"Partial Ostectomy/Sequestrectomy",
  "7560":"Maxillary Sinusotomy Remove Tooth Fragment/Foreign",
  "7910":"Suture Of Recent Small Wounds Up To 5cm","7911":"Complicated Suture Up To 5cm",
  "7912":"Complicated Suture Greater Than 5cm","7920":"Skin Graft",
  "7921":"Collection/Application Autologous Blood Concentrate",
  "7940":"Osteoplasty - Orthognathic Deformities","7941":"Osteotomy - Mandibular Rami",
  "7943":"Osteotomy - Mandibular Rami With Bone Graft","7944":"Osteotomy - Segmented Or Subapical",
  "7945":"Osteotomy - Body Of Mandible","7946":"Lefort I (Maxilla - Total)",
  "7947":"Lefort I (Maxilla - Segmented)","7948":"Lefort II Or III Without Bone Graft",
  "7949":"Lefort II Or III With Bone Graft","7950":"Osseous, Osteoperiosteal, Cartilage Graft",
  "7951":"Sinus Augmentation Via A Lateral Open Approach","7952":"Sinus Augmentation Via A Vertical Approach",
  "7953":"Bone Replacement Graft For Ridge Preservation","7955":"Repair Of Maxillofacial Soft/Hard Tissue Defect",
  "7956":"Guided Tissue Regeneration, Edentulous Area",
  "7960":"Frenulectomy / Frenectomy / Frenotomy","7961":"Buccal/Labial Frenectomy",
  "7962":"Lingual Frenectomy","7963":"Frenuloplasty",
  "7970":"Excision Of Hyperplastic Tissue - Per Arch","7971":"Excision Of Pericoronal Gingiva",
  "7972":"Surgical Reduction Of Fibrous Tuberosity","7979":"Non-Surgical Sialolithotomy",
  "7980":"Surgical Sialolithotomy","7981":"Excision Of Salivary Gland",
  "7982":"Sialodochoplasty","7983":"Closure Of Salivary Fistula",
  "7990":"Emergency Tracheotomy","7991":"Coronoidectomy",
  "7993":"Surgical Placement Of Craniofacial Implant","7995":"Synthetic Graft - Mandible Or Facial Bones",
  "7996":"Implant - Mandible For Augmentation Purposes","7997":"Appliance Removal",
  "7998":"Intraoral Placement Fixation Device W/O Fracture",
  "7999":"Unspecified Oral Surgery Procedure, By Report",
  "5110":"Complete Denture - Maxillary","5120":"Complete Denture - Mandibular",
  "5130":"Immediate Denture - Maxillary","5140":"Immediate Denture - Mandibular",
  "5211":"Max Partial Denture Resin Base","5212":"Mand Partial Denture Resin Base",
  "5213":"Max Partial Denture Cast Metal","5214":"Mand Partial Denture Cast Metal",
  "5221":"Immediate Maxillary Partial Denture - Resin Base","5222":"Immediate Mandibular Partial Denture - Resin Base",
  "5223":"Immediate Maxillary Partial Denture - Cast Metal","5224":"Immediate Mandibular Partial Denture - Cast Metal",
  "5225":"Max Partial Denture - Flexible Base","5226":"Mand Partial Denture - Flexible Base",
  "5227":"Immediate Max Partial Denture - Flexible Base","5228":"Immediate Mand Partial Denture - Flexible Base",
  "5281":"Removable Unilateral Partial Denture",
  "5282":"Removable Unilateral Partial Denture - One Piece Cast Metal, Max",
  "5283":"Removable Unilateral Partial Denture - One Piece Cast Metal, Mand",
  "5284":"Removable Unilateral Partial Denture - One Piece Flexible Base",
  "5286":"Removable Unilateral Partial Denture - One Piece Resin Base",
  "5410":"Adjust Complete Denture Maxillary","5411":"Adjust Complete Denture Mandibular",
  "5421":"Adjust Partial Denture Maxillary","5422":"Adjust Partial Denture Mandibular",
  "5510":"Repair Broken Complete Denture Base","5511":"Repair Broken Complete Denture Base, Mandibular",
  "5512":"Repair Broken Complete Denture Base, Maxillary","5520":"Replace Missing Or Broken Teeth",
  "5610":"Repair Resin Partial Denture Base","5611":"Repair Resin Partial Denture Base, Mandibular",
  "5620":"Repair Cast Framework","5621":"Repair Cast Partial Denture Base, Mandibular",
  "5630":"Repair Or Replace Broken Clasp - Per Tooth","5640":"Replace Broken Teeth - Per Tooth",
  "5650":"Add Tooth To Existing Partial Denture","5660":"Add Clasp To Existing Partial Denture - Per Tooth",
  "5710":"Rebase Complete Maxillary Denture","5711":"Rebase Complete Mandibular Denture",
  "5720":"Rebase Maxillary Partial Denture","5721":"Rebase Mandibular Partial Denture",
  "5725":"Rebase Hybrid Prosthesis","5730":"Reline Complete Maxillary Denture Chairside",
  "5731":"Reline Complete Mandibular Denture Chairside","5740":"Reline Max Partial Denture Chairside",
  "5741":"Reline Mand Partial Denture Chairside","5750":"Reline Complete Max Denture Lab",
  "5751":"Reline Complete Mand Denture Lab","5760":"Reline Max Partial Denture Lab",
  "5761":"Reline Mand Partial Denture Lab","5765":"Soft Liner - Complete Or Partial Removable Denture",
  "5810":"Interim Complete Denture (Maxillary)","5811":"Interim Complete Denture (Mandibular)",
  "5820":"Interim Partial Denture (Maxillary)","5821":"Interim Partial Denture (Mandibular)",
  "5850":"Tissue Conditioning - Maxillary","5851":"Tissue Conditioning - Mandibular",
  "5860":"Overdenture - Complete, By Report","5861":"Overdenture - Partial, By Report",
  "5862":"Precision Attachment","5863":"Overdenture - Complete Maxillary","5864":"Overdenture - Partial Maxillary",
  "5865":"Overdenture - Complete Mandibular","5866":"Overdenture - Partial Mandibular",
  "5867":"Replacement Of Replaceable Part Of Attachment",
  "5875":"Modification Of Removable Prosthesis Following Implant",
  "5876":"Add Metal Substructure To Acrylic Full Denture Per Arch",
  "5899":"Unspecified Removable Prosthodontic Procedure",
  "6205":"Pontic - Indirect Resin Based Composite","6210":"Pontic Cast High Noble Metal",
  "6211":"Pontic Cast Base Metal","6212":"Pontic Cast Noble Metal","6214":"Pontic - Titanium",
  "6240":"Pontic Porcelain Fused High Noble Metal","6241":"Pontic Porcelain Fused Base Metal",
  "6242":"Pontic Porcelain Fused Noble Metal","6243":"Pontic - Porcelain Fused To Titanium",
  "6245":"Pontic Porcelain/Ceramic","6250":"Pontic Resin W/High Noble Metal",
  "6251":"Pontic Resin W/Predominantly Base Metal","6252":"Pontic Resin W/Noble Metal",
  "6253":"Provisional Pontic","6545":"Retainer FPD - Cast/Metal Resin","6548":"Retainer FPD - Porcelain/Ceramic",
  "6549":"Resin Retainer - Resin Bonded Fixed Prosthesis",
  "6930":"Recement Or Rebond Fixed Partial Denture","6940":"Stress Breaker",
  "6950":"Precision Attachment","6980":"Fixed Partial Denture Repair",
  "6985":"Pediatric Partial Denture Fixed","6999":"Unspecified Fixed Prosthodontic Procedure",
  "6010":"Surgical Placement Implant - Endosteal","6011":"Second Stage Implant Surgery",
  "6012":"Surgical Placement - Interim Endosteal Implant","6013":"Surgical Placement Of Mini Implant",
  "6040":"Surgical Placement - Eposteal Implant","6050":"Surgical Placement - Transosteal Implant",
  "6051":"Interim Abutment","6052":"Semi-Precision Attachment Abutment",
  "6055":"Connecting Bar - Implant Or Abutment Supported","6056":"Prefabricated Abutment (Modification, Placement)",
  "6057":"Custom Fabricated Abutment","6058":"Abutment Supported Porcelain/Ceramic Crown",
  "6059":"Abutment Supported Porc Fused To Metal Crown - HNM","6060":"Abutment Supported Porc Fused To Metal Crown - BM",
  "6061":"Abutment Supported Porc Fused To Metal Crown - NM","6062":"Abutment Supported Cast Metal Crown - HNM",
  "6063":"Abutment Supported Cast Metal Crown - BM","6064":"Abutment Supported Cast Metal Crown - NM",
  "6065":"Implant Supported Porcelain/Ceramic Crown","6066":"Implant Supported Porc Fused Metal Crown - Titanium",
  "6067":"Implant Supported Metal Crown - Titanium","6080":"Implant Maintenance Procedures",
  "6081":"Scaling/Debridement Of Single Implant","6083":"Implant Supported Crown - Porc Fused To Noble Alloy",
  "6084":"Implant Supported Crown - Porc Fused To Titanium","6085":"Provisional Implant Crown",
  "6086":"Implant Supported Crown - Predominantly Base Alloys","6087":"Implant Supported Crown - Noble Alloys",
  "6088":"Implant Supported Crown - Titanium","6089":"Accessing And Retorquing Loose Implant Screw",
  "6090":"Repair Implant Prosthesis","6091":"Replacement Attachment - Implant/Abutment Supported Prosthesis",
  "6092":"Recement Or Rebond Implant/Abutment Supported Crown",
  "6093":"Recement Or Rebond Implant/Abutment Supported FPD","6094":"Abutment Supported Crown - Titanium",
  "6095":"Repair Implant Abutment","6096":"Remove Broken Implant Retaining Screw",
  "6100":"Implant Removal","6101":"Debridement Of Periimplant Defect",
  "6102":"Debridement/Osseous Contour Periimplant Defect","6103":"Bone Graft For Repair Of Peri-Implant Defect",
  "6104":"Bone Graft At Time Of Implant Placement","6110":"Implant/Abutment Supp Removable Denture - Edentulous Max",
  "6111":"Implant/Abutment Supp Removable Denture - Edentulous Mand",
  "6112":"Implant/Abutment Supp Removable Denture - Partially Edentulous Max",
  "6113":"Implant/Abutment Supp Removable Denture - Partially Edentulous Mand",
  "6114":"Implant/Abutment Supp Fixed Denture - Edentulous Max",
  "6115":"Implant/Abutment Supp Fixed Denture - Edentulous Mand",
  "6116":"Implant/Abutment Supp Fixed Denture - Partially Edentulous Max",
  "6117":"Implant/Abutment Supp Fixed Denture - Partially Edentulous Mand",
  "6118":"Implant/Abutment Supp Interim Fixed Denture - Mandibular",
  "6119":"Implant/Abutment Supp Interim Fixed Denture - Maxillary",
  "6120":"Implant Supported Retainer - Porc Fused To Titanium",
  "6121":"Implant Supported Retainer For Metal FPD - Base Alloys",
  "6122":"Implant Supported Retainer For Metal FPD - Noble Alloys",
  "6123":"Implant Supported Retainer For Metal FPD - Titanium",
  "6190":"Radiographic/Surgical Implant","6191":"Semi-Precision Abutment - Placement",
  "6192":"Semi-Precision Attachment - Placement","6195":"Abutment Supported Retainer - Porc Fused To Titanium",
  "6198":"Remove Interim Implant Component","6199":"Unspecified Implant Procedure By Report",
  "8010":"Limited Primary Dentition","8020":"Limited Transitional Dentition",
  "8030":"Limited Adolescent Dentition","8040":"Limited Adult Dentition",
  "8050":"Interceptive Primary Dentition","8060":"Interceptive Transition Dentition",
  "8062":"Ortho, Interceptive, Appliance Only","8070":"Comprehensive Transitional Dentition",
  "8080":"Comprehensive Adolescent Dentition","8085":"Invisalign Teen",
  "8090":"Comprehensive Adult Dentition","8095":"Invisalign Full",
  "8096":"Invisalign Express 10","8097":"Invisalign Express 5",
  "8210":"Removable Appliance Therapy","8220":"Fixed Appliance Therapy",
  "8660":"Pre-Ortho Treatment Exam - Monitor Growth/Development",
  "8670":"Ortho Periodic Treatment Visit","8680":"Ortho Retention - PROTECT",
  "8681":"Removable Orthodontic Retainer Adjustment","8690":"Ortho Treatment",
  "8691":"Repair Ortho Appliance","8692":"Replace Lost/Broken Retainer",
  "8693":"Recement Or Rebond Fixed Retainer","8694":"Repair Of Fixed Retainers, Includes Reattachment",
  "8695":"Removal Fixed Ortho Appliance - Non-completed Tx",
  "8698":"Recement Or Re-Bond Fixed Retainer - Maxillary","8699":"Recement Or Re-Bond Fixed Retainer - Mandibular",
  "8701":"Repair Of Fixed Retainer, Includes Reattachment - Max",
  "8702":"Repair Of Fixed Retainer, Includes Reattachment - Mand",
  "8703":"Replacement Of Lost Or Broken Retainer - Max","8704":"Replacement Of Lost Or Broken Retainer - Mand",
  "8999":"Unspecified Orthodontic Procedure, By Report",
  "9110":"Emergency Treatment/Palliative","9120":"Fixed Partial Denture Sectioning",
  "9130":"TMJ - Non-Invasive Physical Therapies","9210":"Local Anesthesia - No Operative Or Surgery Procedure",
  "9211":"Regional Block Anesthesia","9212":"Trigeminal Division Block Anesthesia","9215":"Local Anesthesia",
  "9219":"Evaluation - Moderate/Deep Sedation Or General Anesthesia",
  "9222":"Deep Sedation/General Anesthesia - First 15 Min",
  "9223":"Deep Sedation/General Anesthesia - Each Subsequent 15 Min",
  "9230":"Inhalation Of Nitrous Oxide","9239":"Intravenous Moderate (Conscious) Sedation - 1st 15 Min",
  "9243":"Intravenous Moderate (Conscious) Sedation - Each Subsequent 15 Min",
  "9248":"Non-Intravenous (Conscious) Sedation",
  "9310":"Consultation - Diagnostic Service","9311":"Consultation With Medical Health Care Professional",
  "9410":"House/Extended Care Facility Call","9420":"Hospital Or Ambulatory Surgical Center Call",
  "9430":"Office Visit For Observation","9440":"Office Visit After Hours",
  "9450":"Case Preparation Extended Treatment Plan",
  "9610":"Therapeutic Parenteral Drug Injection, Single Admin",
  "9612":"Therapeutic Parenteral Drugs - 2+ Admins, Different Medications",
  "9613":"Infiltration Of Sustained Release Therapeutic Drug",
  "9630":"Drugs/Medicaments Dispensed In Office For Home Use",
  "9910":"Application Of Desensitizing","9911":"Apply Desensitizing Resin","9920":"Behavior Management",
  "9930":"Treatment Of Complications",
  "9932":"Cleaning/Inspection Removable Complete Denture, Maxillary",
  "9933":"Cleaning/Inspection Removable Complete Denture, Mandibular",
  "9934":"Cleaning/Inspection Removable Partial Denture, Maxillary",
  "9935":"Cleaning/Inspection Removable Partial Denture, Mandibular",
  "9941":"Fabricate Athletic Mouth Guard","9942":"Repair And/Or Reline Of Occlusal Guard",
  "9943":"Occlusal Guard Adjustment",
  "9944":"Occlusal Guard - Hard Appliance, Full Arch","9945":"Occlusal Guard - Soft Appliance, Full Arch",
  "9946":"Occlusal Guard - Hard Appliance, Partial Arch",
  "9950":"Occlusion Analysis Mounted","9951":"Occlusal Adjustment Limited","9952":"Occlusal Adjustment Complete",
  "9961":"Duplicate/Copy Patient's Records","9970":"Enamel Microabrasion","9971":"Odontoplasty - Per Tooth",
  "9972":"External Bleaching - In Office","9973":"Bleaching Per Tooth, External","9974":"Bleaching Per Tooth, Internal",
  "9975":"External Bleaching Home Application","9985":"Sales Tax",
  "9986":"Missed Appointment","9987":"Cancelled Appointment","9988":"Missed Appointment With Notice",
  "9989":"No Show Appointment","9990":"Certified Translation Or Sign-Language Services",
  "9991":"Dental Case Management - Address Appointment Compliance Barriers",
  "9992":"Dental Case Management - Care Coordination",
  "9993":"Dental Case Management - Motivational Interviewing",
  "9994":"Dental Case Management - Patient Education - Oral Health Literacy",
  "9995":"Teledentistry - Synchronous; Real-Time Encounter",
  "9996":"Teledentistry - Synchronous; Info Stored/Forwarded",
  "9999":"Unspecified Adjunctive Procedure, By Report"
};

// ─── FREQUENCY LIST ───────────────────────────────────────
const FREQ = [
  "No Limitation",
  "Eight per 1 year benefit year",
  "Four per Benefit year",
  "Once every 120 Months of Date of Service",
  "Once every 3 Years of Date of Service",
  "Once every 6 Month of Date of Service",
  "Once every 96 Months of Date of Service",
  "Once per 10 Year Date of Service",
  "Once per 12 Month of Date of Service",
  "Once per 12 Year Benefit Year",
  "Once per 18 Month Benefit Year",
  "Once per 2 Year of Date of Service",
  "Once per 24 Month of Date of Service",
  "Once per 3 Month of Date of Service",
  "Once per 36 Month of Date of Service",
  "Once per 48 Month of Date of Service",
  "Once per 5 Year of Date of Service",
  "Once per 60 Month of Date of Service",
  "Once per 7 year of Date of Service",
  "Once per 8 Year of Date of Service",
  "Once per 84 Month of Date of Service",
  "Once per Benefit Year",
  "Once per Five Benefit Years",
  "Once per Lifetime",
  "Once per Seven Benefit Years",
  "Once per Ten Benefit Years",
  "Once per Three Benefit Years",
  "Once per Two Benefit Years",
  "Thrice per 1 Year Benefit Year",
  "Twice per 2 Year Date of Service",
  "Twice per 6 Month Benefit Year",
  "Twice per Benefit Year",
  "Twice per Last 12 Months of Date of Service",
  "Other"
];

// ─── VERIFIED BY NAME ─────────────────────────────────────
function updateVerifiedName(input) {
  input.value = input.value.toUpperCase();
}

// ─── GREEN SELECT FILL ────────────────────────────────────
document.addEventListener('change', e => {
  if (e.target.tagName === 'SELECT') {
    e.target.classList.toggle('has-value', e.target.value !== '');
  }
});

// ─── TOGGLE FUNCTIONS ─────────────────────────────────────
function toggleOON() {
  document.getElementById('oonBox').classList.toggle('visible',
    document.getElementById('networkStatus').value === 'Out');
}
function toggleBenefitOther() {
  document.getElementById('benefitOtherBox').classList.toggle('visible',
    document.getElementById('benefitType').value === 'Other');
}
// Appt Codes toggle
function toggleApptCodes(btn) {
  const wrap = document.getElementById('apptCodesWrap');
  const show = wrap.style.display === 'none';
  wrap.style.display = show ? 'block' : 'none';
  const icon = document.getElementById('apptToggleIcon');
  const label = document.getElementById('apptToggleLabel');
  if (show) {
    icon.innerHTML = '<polyline points="18 15 12 9 6 15"/>';
    label.textContent = 'Collapse Appt Codes';
  } else {
    icon.innerHTML = '<line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/>';
    label.textContent = 'Add Appt Codes';
  }
}

// ─── PROCEDURE TABLE ──────────────────────────────────────
function buildPercInput() {
  return `<div style="display:flex;align-items:stretch;width:100%;height:100%;">
    <input type="text" maxlength="3" placeholder="0" style="flex:1;border:none;outline:none;font-family:inherit;font-size:11px;text-align:right;padding:4px 4px;background:transparent;width:30px;">
    <span style="padding:4px 6px;font-size:10px;font-weight:700;color:var(--dark);background:#F8FAF9;border-left:1px solid var(--border);display:flex;align-items:center;">%</span>
  </div>`;
}
function buildFreqOptions() {
  return '<option value="">–</option>' + FREQ.map(f => `<option value="${f}">${f}</option>`).join('');
}
function buildProcRow(code, tbodyId) {
  const tbody = document.getElementById(tbodyId);
  const tr = document.createElement('tr');
  const desc = code ? (CDT[code] || 'Enter 4-digit code…') : 'Enter 4-digit code…';
  tr.innerHTML = `
    <td class="code-cell"><div class="d-badge"><span class="d-prefix">D</span>
      <input class="code-input" type="text" maxlength="4" value="${code}" placeholder="0000" oninput="updateCodeName(this)">
    </div></td>
    <td class="proc-name">${desc}</td>
    <td style="padding:0;">${buildPercInput()}</td>
    <td><select class="table-select" onchange="handleFreqChange(this)">${buildFreqOptions()}</select></td>
    <td><select class="table-select"><option value="">–</option><option>Yes</option><option>No</option></select></td>
    <td><input type="text" placeholder="–" style="width:100%;border:none;outline:none;font-family:inherit;font-size:11px;padding:6px 8px;background:transparent;"></td>
    <td><button class="remove-btn" onclick="this.closest('tr').remove()" title="Remove">×</button></td>
  `;
  tbody.appendChild(tr);
}
function addProcRow(code = '') { buildProcRow(code, 'procBody'); }
function addApptRow(code = '') { buildProcRow(code, 'apptBody'); }

function updateCodeName(input) {
  let v = input.value.replace(/\D/g,'').slice(0,4);
  input.value = v;
  const nameCell = input.closest('tr').querySelector('.proc-name');
  nameCell.textContent = CDT[v] || (v.length === 4 ? 'Unknown Code' : 'Enter 4-digit code…');
}
function handleFreqChange(sel) {
  const td = sel.parentElement;
  let extra = td.querySelector('.other-input');
  if (sel.value === 'Other') {
    if (!extra) {
      extra = document.createElement('input');
      extra.type = 'text'; extra.className = 'other-input table-select';
      extra.placeholder = 'Describe…'; extra.style.borderTop = '1px solid var(--border)';
      td.appendChild(extra);
    }
  } else if (extra) { extra.remove(); }
}

// ─── UNIFIED TOGGLE SYSTEM ───────────────────────────────
const TOGGLE_EFFECTS = {
  'orthoToggle':         btn => { const show = btn && btn.textContent.trim() === 'Yes'; document.getElementById('orthoBox').classList.toggle('visible', show); },
  'waitToggle':          btn => { const show = btn && btn.textContent.trim() === 'Yes'; document.getElementById('waitBox').classList.toggle('visible', show); },
  'orthoDedToggle':      btn => { const show = btn && btn.textContent.trim() === 'Yes'; document.getElementById('orthoDedBox').classList.toggle('visible', show); },
  'orthoLifetimeToggle': btn => { document.getElementById('orthoMaxLabel').textContent = (btn && btn.textContent.trim() === 'Yes') ? 'Lifetime Max' : 'Annual Max'; },
  'occGuardToggle':      btn => { const show = btn && btn.textContent.trim() === 'Yes'; document.getElementById('occGuardSub').classList.toggle('visible', show); },
  'anesToggle':          btn => {},
  'perioFreqToggle':     btn => { const show = btn && btn.textContent.trim() === 'Yes'; document.getElementById('perioFreqSub').classList.toggle('visible', show); },
};

// IDs that allow multiple buttons active at once
const MULTI_SELECT_GROUPS = ['dedCatToggle'];

document.addEventListener('click', e => {
  if (!e.target.classList.contains('yn-btn')) return;
  const group = e.target.closest('.yn-btns');
  if (!group) return;

  const groupId = group.id || '';

  // Multi-select groups: toggle clicked btn independently, no deselect of siblings
  if (MULTI_SELECT_GROUPS.includes(groupId)) {
    e.target.classList.toggle('active');
    return;
  }

  const alreadyActive = e.target.classList.contains('active');

  // Deselect all siblings
  group.querySelectorAll('.yn-btn').forEach(b => b.classList.remove('active'));

  if (!alreadyActive) {
    e.target.classList.add('active');
    if (TOGGLE_EFFECTS[groupId]) TOGGLE_EFFECTS[groupId](e.target);
  } else {
    // Second click on active — deselect and trigger off state
    if (TOGGLE_EFFECTS[groupId]) TOGGLE_EFFECTS[groupId](null);
  }
});

// ─── INIT ─────────────────────────────────────────────────
window.onload = () => {
  // Set default document title (controls PDF filename)
  document.title = 'GoDentalBrands Insurance Verification Form';
  // Default procedure rows (updated codes)
  ['0120','0140','0150','0220','0274','0330','1110','1120','1206','1351','2391','2740','2950','4346','4910','6010','6058','9222','9230','9944']
    .forEach(c => addProcRow(c));

  // Today's date in MM/DD/YYYY
  const today = new Date();
  const mm = String(today.getMonth() + 1).padStart(2, '0');
  const dd = String(today.getDate()).padStart(2, '0');
  const yyyy = today.getFullYear();
  document.getElementById('callDate').value = `${mm}/${dd}/${yyyy}`;
};

// ─── PHONE MASK (XXX) XXX-XXXX ───────────────────────────
document.addEventListener('input', e => {
  if (!e.target.classList.contains('phone-mask')) return;
  const el = e.target;
  let digits = el.value.replace(/\D/g, '').slice(0, 10);
  let formatted = '';
  if (digits.length > 0) formatted = '(' + digits.slice(0, 3);
  if (digits.length >= 4) formatted += ') ' + digits.slice(3, 6);
  if (digits.length >= 7) formatted += '-' + digits.slice(6, 10);
  el.value = formatted;
});

// ─── DATE MASK (MM/DD/YYYY) ───────────────────────────────
document.addEventListener('input', e => {
  if (!e.target.classList.contains('date-mask')) return;
  const el = e.target;
  let digits = el.value.replace(/\D/g, '').slice(0, 8);
  let formatted = '';
  if (digits.length >= 1) formatted = digits.slice(0, 2);
  if (digits.length >= 3) formatted += '/' + digits.slice(2, 4);
  if (digits.length >= 5) formatted += '/' + digits.slice(4, 8);
  if (digits.length === 2 && el.value.endsWith('/')) formatted += '/';
  if (digits.length === 4 && el.value.endsWith('/')) formatted += '/';
  el.value = formatted;
});

// ─── LIVE % SUFFIX ────────────────────────────────────────
document.addEventListener('input', e => {
  if (!e.target.classList.contains('pct-input')) return;
  const val = e.target.value.replace(/\D/g,'');
  e.target.value = val;
  const liveSpan = e.target.nextElementSibling;
  if (liveSpan && liveSpan.classList.contains('pct-live')) {
    liveSpan.textContent = val ? val + '%' : '';
  }
});

// ─── DYNAMIC DOCUMENT TITLE (Patient Name → PDF filename) ─
function updateDocTitle() {
  const patientField = document.getElementById('patientName');
  const subscriberField = document.getElementById('subscriberName');
  const relationshipSel = document.getElementById('relationship');

  const patientName = patientField ? patientField.textContent.trim() : '';
  const subscriberName = subscriberField ? subscriberField.textContent.trim() : '';
  const relationship = relationshipSel ? relationshipSel.value : '';

  let name = patientName;
  if (!name && relationship === 'Self' && subscriberName) {
    name = subscriberName;
  }

  if (name) name = name.charAt(0).toUpperCase() + name.slice(1);
  document.title = name ? name + ' – Insurance Verification' : 'GoDentalBrands Insurance Verification Form';
}

// ─── FOOTER YEAR ──────────────────────────────────────────
document.getElementById('footerYear').textContent = new Date().getFullYear();
</script>
</body>
</html>
