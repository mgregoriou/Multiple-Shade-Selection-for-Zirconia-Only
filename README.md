<script>
  const shadeMap = {
    // Vita Classic
    "A1": "A1", "A2": "A2", "A3": "A3", "A3.5": "A3.5", "A4": "A4",
    "B1": "B1", "B2": "B2", "B3": "B3", "B4": "B4",
    "C1": "C1", "C2": "C2", "C3": "C3", "C4": "C4",
    "D2": "D2", "D3": "D3", "D4": "D4",

    // Your custom Rx-to-Puck shades
    "OM1": "OM1", "OM2": "OM2", "OM3": "OM3", "1M1": "OM3", "1M2": "A1",
    "2L1.5": "B1", "2L2.5": "A2", "2M1": "A1", "2M2": "A2", "2M3": "A3",
    "2R1.5": "A1", "2R2.5": "A3", "3L1.5": "C2", "3L2.5": "B3", "3M1": "C1",
    "3M2": "D3", "3M3": "A3.5", "3R1.5": "D2", "3R2.5": "A3.5", "4L1.5": "C3",
    "4L2.5": "A3.5", "4M1": "D3", "4M2": "A3.5", "4M3": "A4", "4R1.5": "D3",
    "4R2.5": "A4", "5M1": "D3", "5M2": "A4", "5M3": "A4", "01/110": "A1",
    "1A/120": "A2", "2A/130": "A2", "1C/140": "A3", "2B/210": "A3",
    "1D/220": "A3", "1E/230": "A3", "2C/240": "A3.5", "3A/310": "B3",
    "5B/320": "B4", "2E/330": "B4", "3E/340": "A4", "4A/410": "D3",
    "6B/420": "C2", "4B/430": "C2", "6C/440": "C2", "6D/510": "C3",
    "4C/520": "C3", "3C/530": "C3", "4D/540": "A4", "010": "OM1",
    "020": "OM2", "030": "OM3", "040": "OM3", "BL1": "OM1", "BL2": "OM2",
    "BL3": "OM3", "BL4": "OM3", "B51": "A1", "B52": "B2", "B53": "A2",
    "B54": "A3", "B55": "B3", "B56": "A3", "B59": "A1", "B62": "A1",
    "B63": "A2", "B65": "A3", "B66": "A2", "B67": "B3", "B69": "D4",
    "B77": "C2", "B81": "C3", "B83": "A3.5", "B84": "A4", "B85": "B4",
    "B91": "C1", "B92": "D2", "B94": "C2", "B95": "C2", "B96": "C4"
  };

  function convertShade(shade) {
    const cleaned = shade.trim().toUpperCase();
    return shadeMap.hasOwnProperty(cleaned) ? shadeMap[cleaned] : null;
  }

  function displayShade() {
    const incisalRaw = document.getElementById("incisal").value;
    const bodyRaw = document.getElementById("body").value;
    const gingivalRaw = document.getElementById("gingival").value;

    const incisal = incisalRaw.trim().toUpperCase();
    const body = bodyRaw.trim().toUpperCase();
    const gingival = gingivalRaw.trim().toUpperCase();

    let finalShade = "";

    if (incisal) {
      finalShade = convertShade(incisal);
      if (!finalShade) {
        document.getElementById("output").innerText = `Not found (${incisal})`;
        return;
      }
    } else if (body) {
      finalShade = convertShade(body);
      if (!finalShade) {
        document.getElementById("output").innerText = `Not found (${body})`;
        return;
      }
    } else if (gingival) {
      finalShade = convertShade(gingival);
      if (!finalShade) {
        document.getElementById("output").innerText = `Not found (${gingival})`;
        return;
      }
    } else {
      finalShade = "No shade entered";
    }

    document.getElementById("output").innerText = finalShade;
  }
</script>
