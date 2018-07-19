---
title: Definieren von Makros WHERE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9cf3e87a50362c770d45f00c4dc17ac3d264f611
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380913"
---
# <a name="where-to-define-macros"></a>Definieren von Makros
Definieren von Makros in einer Befehlszeile, Befehlsdatei, Makefile oder der Datei Tools.ini.  
  
 In einem Makefile oder der Datei Tools.ini jede Makrodefinition muss in einer separaten Zeile angezeigt werden und darf nicht mit einem Leerzeichen oder Tabstopp beginnen. Leerzeichen bzw. Tabstopps, um das Gleichheitszeichen werden ignoriert. Alle [Zeichenfolge mit Zeichen](../build/defining-an-nmake-macro.md) literal, einschließlich der umgebenden Anführungszeichen und eingebettete Leerzeichen sind.  
  
 In einer Befehlszeile oder Befehlsdatei Leerzeichen und Tabulatoren begrenzen die Argumente und können nicht das Gleichheitszeichen umschließen. Wenn `string` eingebettete Leerzeichen oder Tabstopps, schließen Sie die Zeichenfolge oder das gesamte Makro in doppelte Anführungszeichen ("").  
  
## <a name="see-also"></a>Siehe auch  
 [Definieren eines NMAKE-Makros](../build/defining-an-nmake-macro.md)