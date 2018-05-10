---
title: Komponente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.component
- component_CPP
dev_langs:
- C++
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bb453e8fe9d21c25292c4e5f94de90dcc67676a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="component"></a>component
Steuert das Sammeln von Browserinformationen oder Abhängigkeitsinformationen aus Quelldateien.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      #pragma component( browser, { on | off }[, references [, name ]] )  
#pragma component( minrebuild, on | off )  
#pragma component( mintypeinfo, on | off )  
```  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="browser"></a>Browser  
 Sie können das Sammeln aktivieren oder deaktivieren, und Sie können angeben, dass bestimmte Namen beim Sammeln von Informationen ignoriert werden.  
  
 Die Aktivierung oder Deaktivierung steuert das Sammeln von Browserinformationen ab dem nächsten Pragma. Zum Beispiel:  
  
```  
#pragma component(browser, off)  
```  
  
 Dieser Code stoppt das Sammeln von Browserinformationen durch den Compiler.  
  
> [!NOTE]
>  Aktiviert das Sammeln von Browserinformationen mit diesem Pragma [Browserinformationen muss zunächst aktiviert](../build/reference/building-browse-information-files-overview.md).  
  
 Die **Verweise** Option kann verwendet werden, mit oder ohne die *Namen* Argument. Mit **Verweise** ohne *Namen* aktiviert oder deaktiviert das Sammeln von verweisen (andere Browserinformationen gesammelt werden allerdings weiterhin). Zum Beispiel:  
  
```  
#pragma component(browser, off, references)  
```  
  
 Dieser Code stoppt das Sammeln von Verweisinformationen durch den Compiler.  
  
 Mit **Verweise** mit *Namen* und **deaktiviert** wird verhindert, dass Verweise auf *Namen* im Suchfenster Informationen angezeigt werden. Verwenden Sie die folgende Syntax, um Namen und Typen zu ignorieren, die für Sie nicht relevant sind, und die Größe von Browserinformationsdateien zu reduzieren. Zum Beispiel:  
  
```  
#pragma component(browser, off, references, DWORD)  
```  
  
 Verweise auf ignoriert **DWORD** ab diesem Punkt. Sie können das Sammeln von Verweisen auf aktivieren `DWORD` Sichern auf mit **auf**:  
  
```  
#pragma component(browser, on, references, DWORD)  
```  
  
 Dies ist die einzige Möglichkeit zum Sammeln von Verweisen auf fortsetzen *Namen*; Sie müssen alle explizit aktivieren *Namen* , die Sie deaktiviert haben.  
  
 Um zu verhindern, dass den Präprozessor erweitert *Namen* (beispielsweise bei der Erweiterung **NULL** auf **0**), Anführungszeichen setzen:  
  
```  
#pragma component(browser, off, references, "NULL")  
```  
  
## <a name="minimal-rebuild"></a>Minimale Neuerstellung  
 Die minimale Wiederaufbaufunktion in Visual C++ erfordert, dass der Compiler C++-Klassenabhängigkeitsinformationen erstellt und speichert, wofür Speicherplatz benötigt wird. Um Speicherplatz zu sparen, können Sie `#pragma component( minrebuild, off )` Wenn es nicht erforderlich, Abhängigkeitsinformationen z. B. in unveränderlichen Headerdateien zu sammeln. Fügen Sie `#pragma component(minrebuild, on)` nach der Sicherung für unveränderlicher Klassen, die Auflistung von Abhängigkeiten zu aktivieren.  
  
## <a name="reduce-type-information"></a>Reduzieren von Typinformationen  
 Die **Mintypeinfo** Option reduziert die Debuginformationen für den angegebenen Bereich. Diese Informationen haben einen beträchtlichen Umfang und wirken sich auf PDB- und OBJ-Dateien aus. Sie können Klassen und Strukturen im mintypeinfo-Bereich nicht debuggen. Die Verwendung der mintypeinfo-Option kann hilfreich sein, um die folgende Warnung zu vermeiden:  
  
```  
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information  
```  
  
 Weitere Informationen finden Sie unter der [minimale Neuerstellung aktivieren](../build/reference/gm-enable-minimal-rebuild.md) (/ Gm)-Compileroption.  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)