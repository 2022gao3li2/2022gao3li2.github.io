---
layout: page
permalink: /gradtrip
title: 毕业旅行
---

日期： 19/12 - 22/12/2022

- [Drive 资料](https://drive.google.com/drive/folders/16TVvGQ4VPbMbt9sHyELML3k7kJK-pKCw?usp=sharing)
- [毕旅 Checklist](https://docs.google.com/document/d/1OSLqFUa81TlHdk6pNwh2FXpEaJEdHwJnTMJ-q2cB4aY/edit?usp=share_link)

## 行程

<table id="itinerary"></table>
<script>
    let t = document.getElementById("itinerary");
    fetch("https://docs.google.com/spreadsheets/d/e/2PACX-1vRHyoENS_9Yx9oSCD0aCkOGWIxGSg0ulf5zYyETp6AnP8bMFvwjmszfbOCGIAI5IK_VYnJwvmfgn5Zm/pub?gid=0&single=true&output=csv")
        .then(res => res.blob())
        .then(blob => blob.text())
        .then(res => {
            console.log(res);
            for (let row of res.split("\n")) {
                let tr = document.createElement("tr");
                for (let cell of row.split(",")) {
                    let td = document.createElement("td");
                    td.innerHTML = cell;
                    tr.appendChild(td);
                }
                t.appendChild(tr);
            }
        });
</script>
