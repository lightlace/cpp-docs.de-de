---
title: "Extrahieren eines Bibliothekmembers"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/EXTRACT (Bibliotheks-Manager-Option)"
  - "EXTRACT (Bibliotheks-Manager-Option)"
  - "-EXTRACT (Bibliotheks-Manager-Option)"
  - "Extrahieren von Bibliotheksmembern"
  - "LIB [C++], Extrahieren von Bibliotheksmembern"
  - "Bibliotheken, Extrahieren von Membern"
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Extrahieren eines Bibliothekmembers
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mithilfe von LIB können Sie eine Objektdatei \(**.obj**\) erstellen, die eine Kopie eines Members aus einer bestehenden Bibliothek enthält.  Um eine Kopie eines Members zu extrahieren, verwenden Sie die folgende Syntax:  
  
```  
LIB library /EXTRACT:member /OUT:objectfile  
```  
  
 Mit diesem Befehl wird eine OBJ\-Datei mit dem Namen *objectfile* erstellt, die eine Kopie eines Members \(`member`\) einer Bibliothek \(*library*\) enthält.  Beim `member`\-Namen wird die Groß\-\/Kleinschreibung berücksichtigt.  Sie können mit diesem Befehl jeweils nur einen Member extrahieren.  Die **\/OUT**\-Option ist erforderlich, da es keinen Standardausgabenamen gibt.  Wenn im angegebenen Verzeichnis bereits eine Datei mit dem Namen *objectfile* vorhanden ist \(oder im aktuellen Verzeichnis, falls für *objectfile* kein Verzeichnis angegeben wurde\), dann ersetzt die extrahierte Objektdatei die bestehende Datei.  
  
## Siehe auch  
 [LIB\-Referenz](../../build/reference/lib-reference.md)