---
title: Angeben einer Inlinedatei | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c0d85436aef5ed48c0a8787f8bce330bf6d3e96
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380104"
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