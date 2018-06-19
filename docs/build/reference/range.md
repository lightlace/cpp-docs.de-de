---
title: -BEREICH | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /RANGE
dev_langs:
- C++
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d06d699500ba3ea441af61a2e2a5a0da3f96903a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374423"
---
# <a name="range"></a>/RANGE
Ändert die Ausgabe von Dumpbin bei Verwendung mit anderen Dumpbin-Optionen, z. B./RAWDATA oder/DISASM an.  
  
## <a name="syntax"></a>Syntax  
  
```  
/RANGE:vaMin[,vaMax]  
```  
  
## <a name="flags"></a>Flags  
 **vaMin**  
 Die virtuelle Adresse, an der Sie der Dumpbin beginnen soll.  
  
 **VaMax** (optional)  
 Die virtuelle Adresse, an der die Dumpbin-Operation beendet werden soll. Wenn nicht angegeben wird, geht die Dumpbin bis zum Ende der Datei.  
  
## <a name="remarks"></a>Hinweise  
 Um die virtuellen Adressen für ein Bild angezeigt wird, verwenden Sie die Zuordnungsdatei für das Bild (RVA + Basis), die **DISASM** oder **/Headers** -Option von Dumpbin oder im Disassemblyfenster in Visual Studio-Debugger.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel **/range** wird verwendet, um die Anzeige der Ändern der **DISASM** Option. In diesem Beispiel wird der Startwert wird als Dezimalzahl angegeben, und der Endwert als eine hexadezimale Zahl angegeben wird.  
  
```  
dumpbin /disasm /range:4219334,0x004061CD t.exe  
```  
  
## <a name="see-also"></a>Siehe auch  
 [DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)