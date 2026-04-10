<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GO Dental - Insurance Verification</title>
<style>
/* --- CORE STYLES --- */
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:'Segoe UI',Arial,sans-serif;background:#f7f7f5}
.page{max-width:860px;margin:0 auto;background:#fff;padding:0 0 3rem; min-height: 100vh;}
.cover{background:#1D9E75;height:72px;display:flex;align-items:center;padding:0 2rem;gap:14px}
.logo-circle{width:42px;height:42px;background:#fff;border-radius:50%;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.logo-circle span{font-size:14px;font-weight:700;color:#1D9E75;letter-spacing:-1px}
.cover-title{color:#fff;font-size:18px;font-weight:600;letter-spacing:.01em}
.cover-sub{color:rgba(255,255,255,.75);font-size:12px;margin-top:2px}
.body{padding:1.5rem 2rem}
.page-title{font-size:26px;font-weight:700;color:#1a1a1a;margin-bottom:4px}
.page-sub{font-size:13px;color:#888;margin-bottom:1.5rem}

/* --- GRIDS & FIELDS --- */
.props-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:0;border:1px solid #e8e8e6;border-radius:8px;overflow:hidden;margin-bottom:1.5rem}
.prop{padding:8px 12px;border-right:1px solid #e8e8e6;border-bottom:1px solid #e8e8e6}
.prop:nth-child(3n){border-right:none}
.prop:nth-last-child(-n+3){border-bottom:none}
.prop-label{font-size:10px;font-weight:600;color:#aaa;text-transform:uppercase;letter-spacing:.06em;margin-bottom:3px}
.prop-val{font-size:13px;color:#333;font-weight:400; outline: none; min-height: 18px;}
.prop-val:focus{color:#1D9E75;}
.prop-val.empty{color:#ccc;font-style:italic}
.prop-val:not(:empty){font-style:normal;}
.prop-tag{display:inline-block;background:#E1F5EE;color:#0F6E56;font-size:11px;font-weight:500;padding:2px 8px;border-radius:20px}

.section{margin-bottom:1.25rem}
.sec-header{display:flex;align-items:center;gap:8px;padding:7px 12px;background:#E1F5EE;border-radius:6px;margin-bottom:8px}
.sec-icon{width:18px;height:18px;flex-shrink:0}
.sec-icon svg{width:18px;height:18px;stroke:#0F6E56;fill:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round}
.sec-title{font-size:13px;font-weight:600;color:#0F6E56;flex:1}

.fields-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:6px;padding:0 4px}
.fields-grid.g3{grid-template-columns:repeat(3,1fr)}
.fields-grid.g4{grid-template-columns:repeat(4,1fr)}
.field-row{display:flex;align-items:stretch;border:1px solid #e8e8e6;border-radius:5px;overflow:hidden;min-height:30px}
.field-row.full{grid-column:1/-1}
.fl{background:#f9f9f8;padding:5px 10px;font-size:11px;font-weight:600;color:#888;min-width:120px;display:flex;align-items:center;border-right:1px solid #e8e8e6;flex-shrink:0}
.fv{background:#fff;padding:5px 10px;font-size:12px;color:#333;flex:1;display:flex;align-items:center; outline: none;}
.fv:focus{background: #f0faf6;}

/* --- DROPDOWNS (NEW) --- */
select.form-select {
  width: 100%;
  border: none;
  background: transparent;
  font-family: inherit;
  font-size: 12px;
  color: #333;
  outline: none;
  cursor: pointer;
  padding: 4px 0;
}
select.form-select:focus { color: #1D9E75; font-weight: 600; }
.fv-dropdown { padding: 0 10px; background: #fff; flex: 1; display: flex; align-items: center; }
.fv-dropdown:focus-within { background: #f0faf6; }

/* --- TOGGLE BUTTONS --- */
.yn-row{display:flex;align-items:center;border:1px solid #e8e8e6;border-radius:5px;overflow:hidden;min-height:30px}
.yn-label{background:#f9f9f8;padding:5px 10px;font-size:11px;font-weight:600;color:#888;flex:1;display:flex;align-items:center;border-right:1px solid #e8e8e6}
.yn-btns{display:flex;gap:0}
.yn-btn{padding:5px 14px;font-size:11px;font-weight:500;color:#aaa;background:#fff;border-left:1px solid #e8e8e6;cursor:pointer; transition: 0.2s;}
.yn-btn:hover{background:#f0faf6;}
.yn-btn.active{background:#E1F5EE;color:#0F6E56;font-weight:700;}

/* --- TABLES --- */
.proc-table{width:100%;border-collapse:collapse;font-size:12px;margin-top:4px}
.proc-table th{background:#f0faf6;color:#0F6E56;font-size:10px;font-weight:600;text-transform:uppercase;letter-spacing:.05em;padding:6px 10px;border:1px solid #e8e8e6;text-align:left}
.proc-table td{padding:0;border:1px solid #e8e8e6;color:#333;vertical-align:middle; outline: none;}
.proc-table td.text-cell { padding: 6px 10px; }
.proc-table td.text-cell:focus { background: #f0faf6; }
.proc-table tr:nth-child(even) td{background:#fafafa}
.proc-code{display:inline-block;background:#E1F5EE;color:#0F6E56;border-radius:4px;padding:1px 6px;font-size:10px;font-weight:600; margin-right: 6px;}

.table-select {
  width: 100%; height: 100%; border: none; background: transparent; 
  padding: 6px 10px; font-family: inherit; font-size: 12px; color: #333; cursor: pointer; outline: none;
}
.table-select:focus { background: #E1F5EE; color: #0F6E56; font-weight: 600; }

/* --- UTILS --- */
.callout{background:#E1F5EE;border-radius:6px;padding:10px 14px;display:flex;gap:10px;align-items:flex-start;margin-bottom:1rem}
.callout-icon{font-size:16px;flex-shrink:0;margin-top:1px}
.callout-text{font-size:12px;color:#0F6E56;line-height:1.5}
.notes-area {border:1px solid #e8e8e6;border-radius:6px;padding:12px 14px;min-height:80px;color:#333;font-size:13px;background:#fafafa; outline: none;}
.notes-area:focus {background: #fff; border-color: #1D9E75;}
.action-bar {text-align: center; margin-top: 2rem;}
.print-btn {background: #1D9E75; color: #fff; border: none; padding: 12px 24px; font-size: 14px; font-weight: 600; border-radius: 6px; cursor: pointer; display: inline-flex; align-items: center; gap: 8px; box-shadow: 0 4px 6px rgba(29, 158, 117, 0.2); transition: 0.2s;}
.print-btn:hover {background: #0F6E56; transform: translateY(-1px);}
.footer{text-align:center;padding-top:1.5rem;border-top:1px solid #e8e8e6;margin-top:1.5rem}
.footer-logo{display:flex;align-items:center;justify-content:center;gap:8px;margin-bottom:4px}
.footer-circle{width:28px;height:28px;background:#1D9E75;border-radius:50%;display:flex;align-items:center;justify-content:center}
.footer-circle span{font-size:9px;font-weight:700;color:#fff}
.footer-name{font-size:13px;font-weight:600;color:#1D9E75}

@media print {
  body {background: #fff;}
  .page {padding: 0; max-width: 100%;}
  .action-bar, .callout {display: none !important;}
  .cover {print-color-adjust: exact; -webkit-print-color-adjust: exact;}
  select { -webkit-appearance: none; -moz-appearance: none; appearance: none; border: none; background: transparent; }
}
</style>
</head>
<body>

<div class="page">
  <div class="cover">
    <div class="logo-circle"><span>GO</span></div>
    <div>
      <div class="cover-title">GO Dental Brands</div>
      <div class="cover-sub">Insurance Verification</div>
    </div>
  </div>

  <div class="body">
    <div class="page-title">Insurance Verification Form</div>
    <div class="page-sub">Fill out the fields directly in your browser.</div>

    <div class="callout">
      <div class="callout-icon">📋</div>
      <div class="callout-text"><strong>How to use:</strong> Select options from the dropdowns, click the Yes/No buttons, and type notes where needed. Click the Print/Save button when finished.</div>
    </div>

    <div class="props-grid">
      <div class="prop"><div class="prop-label">Date</div><div class="prop-val empty" contenteditable="true">MM/DD/YYYY</div></div>
      <div class="prop"><div class="prop-label">Status</div><div class="prop-val"><span class="prop-tag">In progress</span></div></div>
      <div class="prop"><div class="prop-label">Call ref #</div><div class="prop-val empty" contenteditable="true"></div></div>
      <div class="prop"><div class="prop-label">Carrier name</div><div class="prop-val empty" contenteditable="true"></div></div>
      <div class="prop"><div class="prop-label">Insurance phone</div><div class="prop-val empty" contenteditable="true"></div></div>
      <div class="prop"><div class="prop-label">Group #</div><div class="prop-val empty" contenteditable="true"></div></div>
    </div>

    <div class="section">
      <div class="sec-header">
        <div class="sec-icon"><svg viewBox="0 0 24 24"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/></svg></div>
        <span class="sec-title">1 · Plan & carrier info</span>
      </div>
      <div class="fields-grid g3">
        <div class="field-row"><div class="fl">Fee schedule</div><div class="fv" contenteditable="true"></div></div>
        <div class="field-row"><div class="fl">Payor ID #</div><div class="fv" contenteditable="true"></div></div>
        <div class="field-row"><div class="fl">Effective date</div><div class="fv" contenteditable="true"></div></div>
        <div class="field-row"><div class="fl">Group plan name</div><div class="fv" contenteditable="true"></div></div>
        <div class="field-row"><div class="fl">Cal./benefit year</div><div class="fv-dropdown">
          <select class="form-select">
            <option value="">Select...</option>
            <option>Calendar Year</option>
            <option>Benefit Year</option>
          </select>
        </div></div>
        <div class="field-row"><div class="fl">Network</div><div class="fv-dropdown">
          <select class="form-select">
            <option value="">Select...</option>
            <option>In-Network (PPO)</option>
            <option>Out-of-Network (OON)</option>
            <option>HMO / DMO</option>
          </select>
        </div></div>
        <div class="field-row full"><div class="fl">Claims address</div><div class="fv" contenteditable="true"></div></div>
        <div class="field-row"><div class="fl">Representative</div><div class="fv" contenteditable="true"></div></div>
        <div class="field-row"><div class="fl">Insurance phone</div><div class="fv" contenteditable="true"></div></div>
      </div>
    </div>

    <div class="section">
      <div class="sec-header">
        <div class="sec-icon"><svg viewBox="0 0 24 24"><circle cx="12" cy="8" r="4"/><path d="M4 20c0-4 3.6-7 8-7s8 3 8 7"/></svg></div>
        <span class="sec-title">2 · Insured & patient</span>
      </div>
      <div class="fields-grid g3">
        <div class="field-row"><div class="fl">Name of insured</div><div class="fv" contenteditable="true"></div></div>
        <div class="field-row"><div class="fl">DOB</div><div class="fv" contenteditable="true"></div></div>
        <div class="field-row"><div class="fl">Sub ID #</div><div class="fv" contenteditable="true"></div></div>
        <div class="field-row"><div class="fl">Patient name</div><div class="fv" contenteditable="true"></div></div>
        <div class="field-row"><div class="fl">Patient DOB</div><div class="fv" contenteditable="true"></div></div>
      </div>
    </div>

    <div class="section">
      <div class="sec-header">
        <div class="sec-icon"><svg viewBox="0 0 24 24"><rect x="2" y="5" width="20" height="14" rx="2"/><line x1="2" y1="10" x2="22" y2="10"/></svg></div>
        <span class="sec-title">3 · Benefits & maximums</span>
      </div>
      <div class="fields-grid g4">
        <div class="field-row"><div class="fl">Max indiv. $</div><div class="fv" contenteditable="true">$</div></div>
        <div class="field-row"><div class="fl">Max family $</div><div class="fv" contenteditable="true">$</div></div>
        <div class="field-row"><div class="fl">Ded. indiv. $</div><div class="fv" contenteditable="true">$</div></div>
        <div class="field-row"><div class="fl">Ded. family $</div><div class="fv" contenteditable="true">$</div></div>
      </div>
      <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:6px;padding:6px 4px 0">
        <div class="yn-row"><div class="yn-label">Deductible met?</div><div class="yn-btns"><div class="yn-btn">Yes</div><div class="yn-btn">No</div></div></div>
        <div class="yn-row"><div class="yn-label">Family coverage?</div><div class="yn-btns"><div class="yn-btn">Yes</div><div class="yn-btn">No</div></div></div>
        <div class="yn-row"><div class="yn-label">Secondary COB?</div><div class="yn-btns"><div class="yn-btn">Yes</div><div class="yn-btn">No</div></div></div>
      </div>
    </div>

    <div class="section">
      <div class="sec-header">
        <div class="sec-icon"><svg viewBox="0 0 24 24"><polyline points="22 12 18 12 15 21 9 3 6 12 2 12"/></svg></div>
        <span class="sec-title">4 · Coverage percentages</span>
      </div>
      <div class="fields-grid g4">
        <div class="field-row"><div class="fl">Preventive %</div><div class="fv-dropdown">
          <select class="form-select">
            <option value="">%</option><option>100%</option><option>90%</option><option>80%</option><option>70%</option><option>60%</option><option>50%</option><option>0%</option>
          </select>
        </div></div>
        <div class="field-row"><div class="fl">Basic %</div><div class="fv-dropdown">
          <select class="form-select">
            <option value="">%</option><option>100%</option><option>90%</option><option>80%</option><option>70%</option><option>60%</option><option>50%</option><option>0%</option>
          </select>
        </div></div>
        <div class="field-row"><div class="fl">Major %</div><div class="fv-dropdown">
          <select class="form-select">
            <option value="">%</option><option>100%</option><option>90%</option><option>80%</option><option>70%</option><option>60%</option><option>50%</option><option>0%</option>
          </select>
        </div></div>
        <div class="field-row"><div class="fl">Other %</div><div class="fv-dropdown">
          <select class="form-select">
             <option value="">%</option><option>100%</option><option>90%</option><option>80%</option><option>70%</option><option>60%</option><option>50%</option><option>0%</option>
          </select>
        </div></div>

        <div class="field-row"><div class="fl">Endo</div><div class="fv-dropdown">
          <select class="form-select">
            <option value="">Category...</option><option>Basic</option><option>Major</option><option>Not Covered</option>
          </select>
        </div></div>
        <div class="field-row"><div class="fl">Perio</div><div class="fv-dropdown">
          <select class="form-select">
            <option value="">Category...</option><option>Basic</option><option>Major</option><option>Not Covered</option>
          </select>
        </div></div>
        <div class="field-row"><div class="fl">Simple ext.</div><div class="fv-dropdown">
          <select class="form-select">
            <option value="">Category...</option><option>Basic</option><option>Major</option><option>Not Covered</option>
          </select>
        </div></div>
        <div class="field-row"><div class="fl">Surgical ext.</div><div class="fv-dropdown">
          <select class="form-select">
            <option value="">Category...</option><option>Basic</option><option>Major</option><option>Not Covered</option>
          </select>
        </div></div>
      </div>
      
      <div style="display:grid;grid-template-columns:repeat(4,1fr);gap:6px;padding:6px 4px 0">
        <div class="yn-row"><div class="yn-label">Ded. applies?</div><div class="yn-btns"><div class="yn-btn">Y</div><div class="yn-btn">N</div></div></div>
        <div class="yn-row"><div class="yn-label">Diag → ann. max?</div><div class="yn-btns"><div class="yn-btn">Y</div><div class="yn-btn">N</div></div></div>
        <div class="yn-row"><div class="yn-label">Wait period?</div><div class="yn-btns"><div class="yn-btn">Y</div><div class="yn-btn">N</div></div></div>
        <div class="yn-row"><div class="yn-label">Missing tooth cl.?</div><div class="yn-btns"><div class="yn-btn">Y</div><div class="yn-btn">N</div></div></div>
      </div>
    </div>

    <div class="section">
      <div class="sec-header">
        <div class="sec-icon"><svg viewBox="0 0 24 24"><path d="M9 3H5a2 2 0 0 0-2 2v4m6-6h10a2 2 0 0 1 2 2v4M9 3v18m0 0h10a2 2 0 0 0 2-2V9M9 21H5a2 2 0 0 1-2-2V9m0 0h18"/></svg></div>
        <span class="sec-title">5 · Procedures</span>
      </div>
      <table class="proc-table">
        <thead>
          <tr>
            <th style="width: 28%;">Procedure</th>
            <th style="width: 14%;">Covered?</th>
            <th style="width: 12%;">%</th>
            <th style="width: 18%;">Freq</th>
            <th style="width: 10%;">Ded?</th>
            <th style="width: 18%;">Notes</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td class="text-cell"><span class="proc-code">4355</span> Debridement</td>
            <td>
              <select class="table-select">
                <option value="">-</option><option>Yes</option><option>No</option><option>Needs Auth</option>
              </select>
            </td>
            <td>
              <select class="table-select">
                <option value="">%</option><option>100%</option><option>80%</option><option>50%</option><option>0%</option>
              </select>
            </td>
            <td>
              <select class="table-select">
                <option value="">-</option><option>1x / lifetime</option><option>1x / 3 years</option><option>1x / 5 years</option><option>N/A</option>
              </select>
            </td>
            <td>
              <select class="table-select">
                <option value="">-</option><option>Y</option><option>N</option>
              </select>
            </td>
            <td class="text-cell" contenteditable="true">Exam same day?</td>
          </tr>
          
          <tr>
            <td class="text-cell"><span class="proc-code">4910</span> Perio maint.</td>
            <td>
              <select class="table-select">
                <option value="">-</option><option>Yes</option><option>No</option><option>Needs Auth</option>
              </select>
            </td>
            <td>
              <select class="table-select">
                <option value="">%</option><option>100%</option><option>80%</option><option>50%</option><option>0%</option>
              </select>
            </td>
            <td>
              <select class="table-select">
                <option value="">-</option><option>2x / year</option><option>3x / year</option><option>4x / year</option><option>N/A</option>
              </select>
            </td>
            <td>
              <select class="table-select">
                <option value="">-</option><option>Y</option><option>N</option>
              </select>
            </td>
            <td class="text-cell" contenteditable="true">Prophy freq?</td>
          </tr>

          <tr>
            <td class="text-cell"><span class="proc-code">2740</span> Crown</td>
            <td>
              <select class="table-select">
                <option value="">-</option><option>Yes</option><option>No</option><option>Needs Auth</option>
              </select>
            </td>
            <td>
              <select class="table-select">
                <option value="">%</option><option>100%</option><option>80%</option><option>50%</option><option>0%</option>
              </select>
            </td>
            <td>
              <select class="table-select">
                <option value="">-</option><option>1x / 5 years</option><option>1x / 7 years</option><option>1x / 10 years</option><option>N/A</option>
              </select>
            </td>
            <td>
              <select class="table-select">
                <option value="">-</option><option>Y</option><option>N</option>
              </select>
            </td>
            <td class="text-cell" contenteditable="true">Downgrades?</td>
          </tr>

          <tr>
            <td class="text-cell"><span class="proc-code">6010</span> Implants</td>
            <td>
              <select class="table-select">
                <option value="">-</option><option>Yes</option><option>No</option><option>Needs Auth</option>
              </select>
            </td>
            <td>
              <select class="table-select">
                <option value="">%</option><option>100%</option><option>80%</option><option>50%</option><option>0%</option>
              </select>
            </td>
            <td>
              <select class="table-select">
                 <option value="">-</option><option>1x / 5 years</option><option>1x / 7 years</option><option>1x / 10 years</option><option>N/A</option>
              </select>
            </td>
            <td>
              <select class="table-select">
                <option value="">-</option><option>Y</option><option>N</option>
              </select>
            </td>
            <td class="text-cell" contenteditable="true"></td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="section">
      <div class="sec-header">
        <div class="sec-icon"><svg viewBox="0 0 24 24"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/></svg></div>
        <span class="sec-title">Notes</span>
      </div>
      <div class="notes-area" contenteditable="true" placeholder="Add call notes, history, or any additional context here…"></div>
    </div>

    <div class="action-bar">
      <button class="print-btn" onclick="window.print()">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="6 9 6 2 18 2 18 9"></polyline><path d="M6 18H4a2 2 0 0 1-2-2v-5a2 2 0 0 1 2-2h16a2 2 0 0 1 2 2v5a2 2 0 0 1-2 2h-2"></path><rect x="6" y="14" width="12" height="8"></rect></svg>
        Save as PDF / Print
      </button>
    </div>

    <div class="footer">
      <div class="footer-logo">
        <div class="footer-circle"><span>GO</span></div>
        <span class="footer-name">GO Dental Brands</span>
      </div>
    </div>
  </div>
</div>

<script>
  // Script to handle Yes/No toggle buttons (for the standard Yes/No rows)
  document.querySelectorAll('.yn-btns').forEach(group => {
    const buttons = group.querySelectorAll('.yn-btn');
    buttons.forEach(btn => {
      btn.addEventListener('click', () => {
        buttons.forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
      });
    });
  });
</script>

</body>
</html>
