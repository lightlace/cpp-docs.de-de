---
title: -RAWDATA | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /rawdata
dev_langs:
- C++
helpviewer_keywords:
- RAWDATA dumpbin option
- raw data
- -RAWDATA dumpbin option
- /RAWDATA dumpbin option
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 475ec5a827a1453a6f9474762d5be41299fc87e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="rawdata"></a>/RAWDATA
```  
/RAWDATA[:{1|2|4|8|NONE[,number]]  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Option zeigt den Rohdateninhalt des Abschnitts in der Datei. Die Argumente zum Steuern der Anzeige, wie unten dargestellt:  
  
|Argument|Ergebnis|  
|--------------|------------|  
|1|Der Standardwert. Inhalt wird angezeigt, in die hexadezimale Bytes und als ASCII-Zeichen, wenn sie eine gedruckte Darstellung haben.|  
|2|Inhalt wird als 2-Byte-Hexadezimalwerten angezeigt.|  
|4|Inhalt wird als 4-Byte-Hexadezimalwerten angezeigt.|  
|8|Inhalt wird als 8-Byte-Hexadezimalwerten angezeigt.|  
|KEINE|Rohdaten werden unterdrückt. Dieses Argument ist nützlich, um die Steuerung der Ausgabe von/ALL.|  
|*Zahl*|Angezeigten Zeilen werden festgelegt, um eine Breite, die enthält `number` Werte pro Zeile.|  
  
 Nur die [/Headers](../../build/reference/headers.md) DUMPBIN-Option ist verfügbar für die Verwendung in den Dateien erstellt wird, mit der [/GL](../../build/reference/gl-whole-program-optimization.md) -Compileroption.  
  
## <a name="see-also"></a>Siehe auch  
 [DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)