---
title: -LINENUMBERS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /linenumbers
dev_langs: C++
helpviewer_keywords:
- LINENUMBERS dumpbin option
- line numbers
- -LINENUMBERS dumpbin option
- /LINENUMBERS dumpbin option
ms.assetid: 1681d582-2c2f-484e-9920-109959549055
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f81ee61dacab794d457db88532025c05ae5d413b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="linenumbers"></a>/LINENUMBERS
```  
/LINENUMBERS  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Option zeigt COFF-Zeilennummern. Zeilennummern befinden sich in einer Objektdatei, wenn es sich bei der Kompilierung mit Programmdatenbank (/ Zi), C7-kompatibel (/ Z7), oder nur Zeilennummern ("/ Zd"). Eine ausführbare Datei oder DLL enthält COFF-Zeilennummern auf, wenn er mit Debuginfo generieren verknüpft wurde (/ DEBUG).  
  
 Nur die [/Headers](../../build/reference/headers.md) DUMPBIN-Option ist verfügbar für die Verwendung in den Dateien erstellt wird, mit der [/GL](../../build/reference/gl-whole-program-optimization.md) -Compileroption.  
  
## <a name="see-also"></a>Siehe auch  
 [DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)