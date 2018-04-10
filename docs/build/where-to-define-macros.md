---
title: Definieren von Makros WHERE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2e646de4cf67fc249d69fb07789f4c8a3e14bf0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="where-to-define-macros"></a>Definieren von Makros
Definieren von Makros in einer Befehlszeile, Befehlsdatei, Makefile oder der Datei Tools.ini.  
  
 In einem Makefile oder der Datei Tools.ini jede Makrodefinition muss in einer separaten Zeile angezeigt werden und darf nicht mit einem Leerzeichen oder Tabstopp beginnen. Leerzeichen bzw. Tabstopps, um das Gleichheitszeichen werden ignoriert. Alle [Zeichenfolge mit Zeichen](../build/defining-an-nmake-macro.md) literal, einschließlich der umgebenden Anführungszeichen und eingebettete Leerzeichen sind.  
  
 In einer Befehlszeile oder Befehlsdatei Leerzeichen und Tabulatoren begrenzen die Argumente und können nicht das Gleichheitszeichen umschließen. Wenn `string` eingebettete Leerzeichen oder Tabstopps, schließen Sie die Zeichenfolge oder das gesamte Makro in doppelte Anführungszeichen ("").  
  
## <a name="see-also"></a>Siehe auch  
 [Definieren eines NMAKE-Makros](../build/defining-an-nmake-macro.md)