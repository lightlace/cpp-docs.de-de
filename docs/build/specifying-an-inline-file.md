---
title: Angeben einer Inlinedatei | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ef2183390b2aca2fb54e1468bd59e697374a355a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-an-inline-file"></a>Angeben einer Inlinedatei
Geben Sie zwei spitzen Klammern (<<) im Befehl, auf dem *Filename* angezeigt werden soll. Die spitzen Klammern nicht mit der makroerweiterung eines.  
  
## <a name="syntax"></a>Syntax  
  
```  
<<[filename]  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Befehl ausgeführt wird, werden durch die spitzen Klammern ersetzt *Filename*, falls angegeben, oder durch einen eindeutigen Namen von NMAKE generiert. Wenn angegeben, *Filename* spitzen Klammern ohne ein Leerzeichen oder Tabstopp folgen müssen. Ein Pfad ist zulässig. Keine Erweiterung ist erforderlich, oder angenommen. Wenn *Filename* angegeben ist, wird die Datei wird erstellt, in der aktuellen oder angegebenen Verzeichnis, überschreiben die vorhandene Datei mit diesem Namen; andernfalls wird es in der TMP-Verzeichnis erstellt (das aktuelle Verzeichnis oder wenn TMP-Umgebungsvariable ist nicht definiert). Bei Verwendung einer früheren *Filename* wird wiederverwendet, NMAKE ersetzt die vorherige Datei.  
  
## <a name="see-also"></a>Siehe auch  
 [Inlinedateien in einem Makefile](../build/inline-files-in-a-makefile.md)