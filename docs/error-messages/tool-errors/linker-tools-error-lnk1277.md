---
title: "Linkertoolfehler LNK1277"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1277"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1277"
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1277
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Objektdatensatz wurde in PGD nicht gefunden \(Dateiname\)  
  
 Bei der Verwendung von [\/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md) stimmte der Pfad einer der angegebenen LIB\-, DEF\- oder OBJ\-Dateien nicht mit dem bei \/LTCG:PGINSTRUMENT vorhandenen Pfad überein.  Die Ursache hierfür liegt möglicherweise in einer Änderung der LIB\-Umgebungsvariable nach \/LTCG:PGINSTRUMENT.  Der vollständige Pfad zu den Eingabedateien ist in der PGD\-Datei gespeichert.  
  
 \/LTCG:PGOPTIMIZE erfordert, dass die Eingaben denen in der \/LTCG:PGINSTRUMENT\-Phase entsprechen.  
  
 Zum Vermeiden dieser Warnung bestehen folgende Möglichkeiten:  
  
-   Führen Sie \/LTCG:PGINSTRUMENT aus, wiederholen Sie alle Testläufe, und führen Sie \/LTCG:PGOPTIMIZE aus.  
  
-   Setzen Sie die LIB\-Umgebungsvariable auf den Wert zurück, der bei der Ausführung von \/LTCG:PGINSTRUMENT vorhanden war.  
  
 Von der Verwendung von \/LTCG:PGUPDATE zur Umgehung von LNK1277 wird abgeraten.