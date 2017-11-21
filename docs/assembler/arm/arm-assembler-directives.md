---
title: ARM-Assemblydirektiven | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1fee551d667b40b3fc36b3ca1f91e093148083a5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="arm-assembler-directives"></a>ARM-Assemblyanweisungen
Meistens, verwendet der Microsoft-ARM-Assembler die ARM-Assemblysprache, die in Kapitel 7 dokumentiert ist die [ARM Assembler Tools Guide](http://go.microsoft.com/fwlink/?LinkId=246102). Allerdings unterscheiden sich die Microsoft-Implementierungen von einigen Assemblydirektiven aus ARM-Assemblydirektiven ein. In diesem Artikel werden die Unterschiede erläutert.  
  
## <a name="microsoft-implementations-of-arm-assembly-directives"></a>Microsoft-Implementierungen von ARM-Assemblydirektiven  
 BEREICH  
 Der Microsoft-ARM-Assembler unterstützt diese strukturbereichattribute: AUSZURICHTEN, CODE CODEALIGN Daten NOINIT READONLY Lese-/SCHREIBMODUS ZIEHPUNKT, ARM.  
  
 Alle außer DAUMEN und ARM funktioniert wie beschrieben in der [ARM Assembler Tools Guide](http://go.microsoft.com/fwlink/?LinkId=246102).  
  
 Der Microsoft-ARM-Assembler gibt ZIEHPUNKT an, dass ein Codeabschnitt Thumb-Code enthält, und die Standardeinstellung für Codeabschnitten ist.  ARM gibt an, dass der Abschnitt ARM-Code enthält.  
  
 ATTR  
 Wird nicht unterstützt.  
  
 CODE16  
 Nicht unterstützt, da impliziert Pre-UAL Thumb-Syntax, die der Microsoft-ARM-Assembler nicht zulässt.  Verwenden Sie stattdessen, die THUMB-Direktive, zusammen mit der Syntax für die Benutzerzugriffsprotokollierung.  
  
 ALLGEMEINE  
 Spezifikation eine Ausrichtung für die allgemeine Region wird nicht unterstützt.  
  
 DCDO  
 Wird nicht unterstützt.  
  
 DN QN, "SN".  
 Die Spezifikation eines Typs oder einer Klasse auf die Register-Alias wird nicht unterstützt.  
  
 EINTRAG  
 Wird nicht unterstützt.  
  
 EQU  
 Die Spezifikation eines Typs für die definiertes Symbol wird nicht unterstützt.  
  
 EXPORT und GLOBAL  
 ```  
EXPORTsym {[type]}  
```  
  
 `sym`ist das Symbol exportiert werden soll.  `[type]`, wenn angegeben, kann es sich um `[DATA]` um anzugeben, dass das Symbol auf Daten verweist oder `[FUNC]` , um anzugeben, dass das Symbol auf Code verweist.  
  
 Globale ist ein Synonym für den EXPORT aus.  
  
 EXPORTAS  
 Wird nicht unterstützt.  
  
 FRAME  
 Wird nicht unterstützt.  
  
 Funktion und PROC  
 Obwohl die Assembly-Syntax die Angabe einer benutzerdefinierten unterstützt Aufrufkonvention für Prozeduren durch Auflisten der Register, die Aufrufer-speichern und die aufgerufene Automatisches Speichern, werden der Microsoft-ARM-Assembler akzeptiert der Syntax, ignoriert jedoch die Register-Listen.  Die Debuginformationen, die durch den Assembler erstellt wird, unterstützt nur die Standardaufrufkonvention.  
  
 Importieren und "extern"  
 ```  
IMPORT sym{, WEAK alias{, TYPE t}}  
```  
  
 `sym`ist der Name des Symbols importiert werden sollen.  
  
 Wenn der SCHWACHE `alias` angegeben wird, bedeutet dies, dass `sym` eine schwache extern ist. Wenn keine Definition für ihn zum Zeitpunkt der Verknüpfung gefunden wird, und klicken Sie dann alle Verweise darauf binden stattdessen an `alias`.  
  
 Wenn Typ `t` angegeben ist, klicken Sie dann `t` gibt an, wie der Linker versucht werden soll, zum Auflösen `sym`.  Diese Werte für `t` sind möglich:   
1 – Führen Sie eine Bibliothek nach nicht`sym`  
2 – Ausführen einer Suche Bibliothek für`sym`  
3 –`sym` ist ein Alias für `alias` (Standard)  
  
 "Extern" ist ein Synonym für den IMPORT, außer dass `sym` wird nur aus, wenn Verweise darauf in der aktuellen Assembly importiert.  
  
 MACRO  
 Die Verwendung einer Variablen zum Speichern des Bedingung Codes eines Makros wird nicht unterstützt. Standardwerte für Makro werden nicht unterstützt.  
  
 NOFP  
 Wird nicht unterstützt.  
  
 ABONNIEREN, GÜLTIGKEITSDAUER (TTL), SUBT  
 Nicht unterstützt, da der Microsoft-ARM-Assembler Angebote nicht erstellt.  
  
 PRESERVE8  
 Wird nicht unterstützt.  
  
 UMSETZUNG  
 `RELOC n`kann nur eine Anweisung oder ein Daten-Definition-Direktive folgen. Es gibt keine "Anonym"Symbol", die verschoben werden kann.  
  
 ERFORDERN  
 Wird nicht unterstützt.  
  
 REQUIRE8  
 Wird nicht unterstützt.  
  
 THUMBX  
 Nicht unterstützt, da der Microsoft-ARM-Assembler nicht den Thumb-2ee nicht-Anweisungssatz unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Befehlszeilenreferenz des ARM-Assembler](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [Diagnosemeldungen des ARM-Assemblers](../../assembler/arm/arm-assembler-diagnostic-messages.md)