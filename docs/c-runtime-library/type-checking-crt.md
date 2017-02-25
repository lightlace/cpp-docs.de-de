---
title: "Typ&#252;berpr&#252;fung (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.types"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Überprüfen des Typs"
  - "Typüberprüfung"
  - "Variablenargumentefunktionen"
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Typ&#252;berpr&#252;fung (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Compiler führt eingeschränkte Typüberprüfung auf Funktionen, die eine variable Anzahl von Argumenten akzeptieren können, wie folgt aus:  
  
|Funktionsaufruf|Typ\-überprüfte Argumente|  
|---------------------|-------------------------------|  
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|Erstes Argument \(Formatzeichenfolge\)|  
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|Erste zwei Argumente \(Datei oder Puffer und Formatzeichenfolge\)|  
|`_snprintf_s`|Erste drei Argumente \(Datei oder Puffer, Anzahl und Formatzeichenfolge\)|  
|`_open`|Erste zwei Argumente \(Pfad und `_open`\-Flag\)|  
|`_sopen_s`|Erste drei Argumente \(Pfad, `_open` und Freigabenmodus Flag\)|  
|`_execl`, `_execle`, `_execlp`, `_execlpe`|Erste zwei Argumente \(Pfad und erster Argumentzeiger\)|  
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|Erste drei Argumente \(Modusflag, Pfad und erster Argumentzeiger\)|  
  
 Der Compiler führt die gleiche eingeschränkte Typüberprüfung auf den Breitzeichenentsprechungen dieser Funktionen aus.  
  
## Siehe auch  
 [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)