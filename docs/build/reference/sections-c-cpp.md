---
title: "SECTIONS (C/C++)"
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
  - "SECTIONS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SECTIONS-Anweisung in .def-Dateien"
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# SECTIONS (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Durch die Anweisung wird ein Abschnitt mit einer oder mehreren `definitions` eingeleitet, die Zugriffsspezifizierer für Abschnitte in der Projektausgabedatei darstellen.  
  
```  
SECTIONS  
definitions  
```  
  
## Hinweise  
 Jede Definition muss in einer eigenen Zeile stehen.  Das `SECTIONS`\-Schlüsselwort kann sich in derselben Zeile wie die erste Definition oder in einer eigenen, vorangestellten Zeile befinden.  Die DEF\-Datei kann eine oder mehrere `SECTIONS`\-Anweisungen enthalten.  
  
 Mit dieser `SECTIONS`\-Anweisung werden Attribute für einen oder mehrere Abschnitte in der Abbilddatei festgelegt. Sie kann zum Überschreiben der Standardattribute für beliebige Abschnittstypen verwendet werden.  
  
 Die Syntax der Definition lautet:  
  
 `.section_name specifier`  
  
 wobei `.section_name` dem Namen eines Abschnitts im Programmabbild und `specifier`einem oder mehreren der folgenden Zugriffsmodifizierer entspricht:  
  
|Modifizierer|**Beschreibung**|  
|------------------|----------------------|  
|`EXECUTE`|Der betreffende Abschnitt ist ausführbar|  
|`READ`|Ermöglicht Lesevorgänge für Daten|  
|`SHARED`|Gibt den Abschnitt für alle Prozesse frei, die das Abbild laden|  
|`WRITE`|Ermöglicht Schreibvorgänge für Daten|  
  
 Spezifizierer müssen durch ein Leerzeichen voneinander getrennt werden.  Beispiel:  
  
```  
SECTIONS  
.rdata READ WRITE  
```  
  
 `SECTIONS` kennzeichnet den Beginn einer Liste mit `definitions` des Abschnitts.  Jede `definition` muss in einer eigenen Zeile stehen.  Das `SECTIONS`\-Schlüsselwort kann sich in derselben Zeile wie die erste `definition` oder in einer vorangestellten Zeile befinden.  Die DEF\-Datei kann eine oder mehrere `SECTIONS`\-Anweisungen enthalten.  Das `SEGMENTS`\-Schlüsselwort wird als Synonym für `SECTIONS` unterstützt.  
  
 In älteren Versionen von Visual C\+\+ wurde Folgendes unterstützt:  
  
```  
section [CLASS 'classname'] specifier  
```  
  
 Das `CLASS`\-Schlüsselwort wird zwar aus Kompatibilitätsgründen unterstützt, es wird jedoch ignoriert.  
  
 Alternativ können Abschnittsattribute auch mit der [\/SECTION](../../build/reference/section-specify-section-attributes.md)\-Option festgelegt werden.  
  
## Siehe auch  
 [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)