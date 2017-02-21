---
title: "_ITERATOR_DEBUG_LEVEL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ITERATOR_DEBUG_LEVEL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ITERATOR_DEBUG_LEVEL"
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# _ITERATOR_DEBUG_LEVEL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Makro `_ITERATOR_DEBUG_LEVEL` \(IDL\) löst ab und kombiniert die Funktionen der Makros [\_SECURE\_SCL](../standard-library/secure-scl.md) \(SCL\) und [\_HAS\_ITERATOR\_DEBUGGING](../standard-library/has-iterator-debugging.md) \(AUSGEBLENDET\).  
  
## Makrowerte  
 Die folgenden Tabellen enthalten eine Zusammenfassung der Werte für die Makros `_SECURE_SCL` und `_HAS_ITERATOR_DEBUGGING` und schließlich zusammengefasst, wie diese Werte durch das `_ITERATOR_DEBUG_LEVEL`\-Makro ersetzt werden.  
  
 Im folgenden Abschnitt werden die möglichen Werte des SCL und der AUSGEBLENDETEN Makros.  
  
 SCL\=0  
 Deaktiviert überprüften Iteratoren.  
  
 SCL\=1  
 Aktiviert überprüfte Iteratoren.  
  
 HID\=0  
 Deaktiviert Iteratordebugging in Debugbuilds.  
  
 HID\=1  
 Ermöglicht Iteratordebugging in Debugbuilds.  HID kann nicht für Releasebuilds aktiviert werden.  
  
 Die folgende Tabelle beschreibt, wie die IDL\-Makrowerte das SCL und die AUSGEBLENDETEN Makrowerte ablösen.  
  
|Kompilierungsmodus|Neues Makro|Alte Makros|**Beschreibung**|  
|------------------------|-----------------|-----------------|----------------------|  
|**Debuggen**||||  
||IDL\=0|SCL\=0, HID\=0|Deaktiviert überprüften Iteratoren und deaktivieren Iteratordebugging.|  
||IDL\=1|SCL\=1, HID\=0|Aktiviert überprüfte Iteratoren und deaktiviert Iteratordebugging.|  
||IDL\=2 \(Standard\)|SCL\= \(gilt nicht\), HID\=1|Standardmäßig aktiviert Iteratordebugging; überprüfte Iteratoren sind nicht relevant.|  
|**Release**||||  
||IDL\=0 \(Standard\)|SCL\=0|Standardmäßig überprüften Sperrmechanismen Iteratoren.|  
||IDL\=1|SCL\=1|Aktiviert überprüfte Iteratoren; Iteratordebugging ist nicht relevant.|  
  
## Hinweise  
 Im Releasemodus wird ein Fehler ausgegeben, wenn Sie IDL\=2. angeben.  
  
 Da die `_SECURE_SCL` und `_HAS_ITERATOR_DEBUGGING`\-Makros ähnliche Funktionen unterstützen, sind Benutzer häufig unsicher, die in einer bestimmten Situation zu verwenden das Makro und Makrowert.  Um dieses Problem zu beheben, wird empfohlen nur das Makro `_ITERATOR_DEBUG_LEVEL` verwenden.  
  
## Siehe auch  
 [Sichere Bibliotheken: C\+\+\-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)