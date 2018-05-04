---
title: -CLRHEADER | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRHEADER
dev_langs:
- C++
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5896e12d5e3b3b3984884388d11c6380e900d73d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="clrheader"></a>/CLRHEADER
```  
/CLRHEADER file  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 `file`  
 Eine Bilddatei mit erstellten ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="remarks"></a>Hinweise  
 CLRHEADER zeigt Informationen über die in jeder verwalteten Anwendung verwendet. Die Ausgabe zeigt den Speicherort und die Größe in Bytes, die .NET Header und die Abschnitte in der Kopfzeile an.  
  
 Nur die [/Headers](../../build/reference/headers.md) DUMPBIN-Option ist verfügbar für die Verwendung in den Dateien erstellt wird, mit der [/GL](../../build/reference/gl-whole-program-optimization.md) -Compileroption.  
  
 Beim CLRHEADER auf eine Datei verwendet wird, die mit "/ CLR" kompiliert wurde, ergibt sich eine **Clr-Header:** Abschnitt in der Dumpbin-Ausgabe.  Der Wert der **Flags** gibt an, welche Option "/ CLR" verwendet wurde:  
  
-   0 – "/ CLR" (Image darf nativen Code).  
  
 Sie können auch programmgesteuert überprüfen, wenn ein Bild für die common Language Runtime erstellt wurde.  Weitere Informationen finden Sie unter [wie: bestimmen, ob ein Bild systemeigen oder CLR ist](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).  
  
 Die **/CLR: pure** und **/CLR: safe** Compileroptionen sind in Visual Studio 2015 als veraltet markiert und wird in einer zukünftigen Version des Compilers entfernt. Code, der "rein" oder "sicheren" sein muss, sollten zu C#-portiert werden. 
  
## <a name="see-also"></a>Siehe auch  
 [DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)