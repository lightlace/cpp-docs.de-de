---
title: "ANSI C-Kompatibilit&#228;t"
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
  - "Ansi"
dev_langs: 
  - "C++"
  - "C"
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
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# ANSI C-Kompatibilit&#228;t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Namenskonvention für alle Microsoft\-Besonderebezeichner im Laufzeitsystem \(wie Funktionen, Makros, Konstanten, Variablen und Typdefinitionen\) ist ANSI\-kompatibel.  In dieser Dokumentation wird jede Laufzeitfunktion, die den Standards ANSI\/ISO C folgt, als nicht kompatibel ANSI erwähnt.  ANSI\-kompatible Anwendungen sollten diese kompatiblen Funktionen der ANSI nur verwenden.  
  
 Die Namen von Microsoft\-Besonderefunktionen und von globalen Variablen beginnen mit einem Unterstrich einzelnen.  Diese Namen können, im Kontext des Codes nur lokal überschrieben werden.  Wenn Sie Microsoft\-Ablaufheaderdateien einschließen, können Sie das Microsoft\-Besonderen Funktion mit dem Namen `_open` jedoch lokal überschreiben, indem Sie eine lokale Variable mit demselben Namen deklarieren.  Sie können diesen Namen für eigene globale Funktion oder globale Variable nicht verwenden.  
  
 Die Namen von Microsoft\-Besonderemakros und von Manifestkonstanten beginnen mit zwei Unterstrichen oder mit einem einzelnen führende Unterstrich, der unmittelbar auf einen Großbuchstaben folgt.  Der Gültigkeitsbereich dieser Bezeichner ist Absolute.  Beispielsweise können Sie den Microsoft\-Besonderebezeichner **\_UPPER** nicht aus diesem Grund verwenden.  
  
## Siehe auch  
 [Kompatibilität](../c-runtime-library/compatibility.md)