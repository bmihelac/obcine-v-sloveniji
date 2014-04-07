obcine-v-sloveniji
==================

Vir:

https://www.stat.si/obcinevstevilkah/Default.aspx?leto=2013

::

    var rows = [],
        regija = null;

    $("#ctl00_RadTreeView1 > ul > li").each(function() {
      regija =  $("> div > span.rtIn", $(this)).text();
      $("> ul > li", $(this)).each(function() {
        rows.push([regija, $(this).text().trim()]);
      });
    });

    var obcine_json = JSON.stringify(rows, null, 4)
    obcine_csv = rows.map(function(r) { return r.join(','); }).join("\n");
