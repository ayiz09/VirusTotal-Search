# VirusTotal-Search
This search is to find or hunt malware and use that to defense organisation.

## Find Specific Malware
1. Find any released ioc.
2. Search on VT-Graph.

![VT-Graph](https://user-images.githubusercontent.com/19946447/153810991-3f903554-7a7a-46f7-bc58-d6b11a5933a9.PNG)

3. Click Down-arrow symbol.

![VT-Graph_v2](https://user-images.githubusercontent.com/19946447/153811508-7f95b600-9f0d-404c-8a9e-68a4091842c4.PNG)

4. And choose with detection.

![VT-Graph_v3](https://user-images.githubusercontent.com/19946447/153811701-fc3b3750-af3c-4176-a0da-1c655905a194.PNG)

From all this hashes you can update into your AV to block it.

## Find recent ransomware sample

Use filter in VT-Entreprise
```
engine: *ryuk* fs:2022-02-1+ type:peexe have:crowdsourced_yara_rule
```

fs: first seen.  
type: type of file.  
have: modifier.  

Find some sample not detected (using **NOT**):
```
engine: *ryuk* fs:2022-02-1+ type:peexe NOT have:crowdsourced_yara_rule
```

## Find Spearphising malware
Traditional initial vector is attachment , so you can search for document contain macro:  
```
tag:attachment type:docx fs:2022-02-01+ p:5+ s:2+ tag:macros
```
p: positive detection.    
s: size of file.  

## Most Common CVE used by Adversaries
Exploited by malware and you can patch it.  
```
tag:cve* tag:attachment fs:2022-02-01+
```

