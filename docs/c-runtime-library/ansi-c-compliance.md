---
title: "ANSI C-Kompatibilit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Ansi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ANSI [C++], C-Standard"
  - "Kompatibilität [C++], ANSI-C"
  - "Kompatibilität mit ANSI C"
  - "Konventionen [C++], Microsoft-Erweiterungen"
  - "Microsoft-Erweiterungen, Benennungskonventionen"
  - "Benennungskonventionen [C++], Microsoft-Bibliothek"
  - "Unterstriche"
  - "Unterstriche, Zeilenabstand"
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ANSI C-Kompatibilit&#228;t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Namenskonvention für alle Microsoft\-Besonderebezeichner im Laufzeitsystem \(wie Funktionen, Makros, Konstanten, Variablen und Typdefinitionen\) ist ANSI\-kompatibel.  In dieser Dokumentation wird jede Laufzeitfunktion, die den Standards ANSI\/ISO C folgt, als nicht kompatibel ANSI erwähnt.  ANSI\-kompatible Anwendungen sollten diese kompatiblen Funktionen der ANSI nur verwenden.  
  
 Die Namen von Microsoft\-Besonderefunktionen und von globalen Variablen beginnen mit einem Unterstrich einzelnen.  Diese Namen können, im Kontext des Codes nur lokal überschrieben werden.  Wenn Sie Microsoft\-Ablaufheaderdateien einschließen, können Sie das Microsoft\-Besonderen Funktion mit dem Namen `_open` jedoch lokal überschreiben, indem Sie eine lokale Variable mit demselben Namen deklarieren.  Sie können diesen Namen für eigene globale Funktion oder globale Variable nicht verwenden.  
  
 Die Namen von Microsoft\-Besonderemakros und von Manifestkonstanten beginnen mit zwei Unterstrichen oder mit einem einzelnen führende Unterstrich, der unmittelbar auf einen Großbuchstaben folgt.  Der Gültigkeitsbereich dieser Bezeichner ist Absolute.  Beispielsweise können Sie den Microsoft\-Besonderebezeichner **\_UPPER** nicht aus diesem Grund verwenden.  
  
## Siehe auch  
 [Kompatibilität](../c-runtime-library/compatibility.md)