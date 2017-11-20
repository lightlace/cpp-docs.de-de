---
title: Erstellen von Text Inlinedatei | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 174160657e5494f5566fd0828815b3c0f1b3d601
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="creating-inline-file-text"></a>Erstellen von Text für die Inlinedatei
Inlinedateien sind temporär oder dauerhaft ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      inlinetext  
.  
.  
.  
<<[KEEP | NOKEEP]  
```  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie *Inlinetext* in der ersten Zeile nach dem Befehl. Markieren Sie das Ende mit doppelten spitzen Klammern (<<) am Anfang einer separaten Zeile. Die Datei enthält alle *Inlinetext* vor den begrenzenden Klammern. Die *Inlinetext* makroerweiterungen und Ersetzungen, jedoch keine Richtlinien oder Makefile Kommentare haben können. Leerzeichen, Tabulatoren und Zeilenumbruchzeichen werden als solcher behandelt.  
  
 Eine temporäre Datei für die Dauer der Sitzung vorhanden ist und anderen Befehlen verwendet werden kann. Geben Sie **behalten** nach der schließenden spitzen Klammern um die Datei nach der NMAKE-Sitzung beibehalten wird eine unbenannte Datei auf dem Datenträger mit dem generierten Dateinamen beibehalten. Geben Sie **NOKEEP** oder kein Zeichen für eine temporäre Datei. **Behalten Sie** und **NOKEEP** sind nicht in der Groß-/Kleinschreibung beachtet.  
  
## <a name="see-also"></a>Siehe auch  
 [Inlinedateien in einem Makefile](../build/inline-files-in-a-makefile.md)