---
aliases: 
tags: 
date created: 2024-12-20T13:11:15-05:00
date modified: 2024-12-20T13:11:15-05:00
---

%% Begin Waypoint %%
- **[[ID 1]]**
- **[[ID 2]]**

%% End Waypoint %%

```dataviewjs
const framework = dv.current().framework || "framework_here";
const allConnections = dv.pages('"Framework/TopLevel"').flatMap(page => {
    return page.file.content.match(new RegExp(`${framework}\\.\\w+:: \\[\\[.*?\\]\\] .*`, 'g')) || [];
}).map(line => {
    const match = line.match(/(.*):: \[\[(.*?)\]\] (.*)/);
    if (match) {
        const [_, key, target, metadata] = match;
        return { key, target, metadata: JSON.parse(metadata || '{}'), source: page.file.name };
    }
    return null;
}).filter(Boolean);

dv.table(["Source", "Key", "Target", "Metadata"], 
    allConnections.map(c => [c.source, c.key, c.target, JSON.stringify(c.metadata)]));
```

```dataviewjs
const framework = dv.current().framework || "framework_here";
const frameworkObject = dv.pages('"Framework/TopLevel"').flatMap(page => {
    return page.file.content.match(new RegExp(`${framework}\\.\\w+:: \\[\\[.*?\\]\\] .*`, 'g')) || [];
}).reduce((acc, line) => {
    const match = line.match(/(.*):: \[\[(.*?)\]\] (.*)/);
    if (match) {
        const [_, key, target, metadata] = match;
        if (!acc[key]) acc[key] = [];
        acc[key].push({ target, metadata: JSON.parse(metadata || '{}'), source: page.file.name });
    }
    return acc;
}, {});

dv.paragraph(JSON.stringify(frameworkObject, null, 2));
```
