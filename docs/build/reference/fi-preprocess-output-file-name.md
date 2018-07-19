---
title: -Fi (Ausgabedateiname vorverarbeiten) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Fi
dev_langs:
- C++
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e7fe5ffbb8a6ccdd5ef02d2cf3feb6b94d48233
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371511"
---
# <a name="fi-preprocess-output-file-name"></a>/Fi (Ausgabedateiname vorverarbeiten)
Gibt den Namen der Ausgabedatei an, in dem die [/p (Vorverarbeitung in eine Datei)](../../build/reference/p-preprocess-to-a-file.md) Compileroption schreibt vorverarbeiteten Ausgabedatei.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Fipathname  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`pathname`|Der Name und Pfad der Ausgabedatei erstellt, indem die **/p** -Compileroption.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der **/Fi** (Compileroption) in Kombination mit der **/p** -Compileroption.  
  
 Wenn Sie angeben, dass nur einen Pfad zu der `pathname` Parameter, der Basisname der Quelldatei als den Namen der vorverarbeiteten Ausgabedatei verwendet wird. Die `pathname` Parameter erfordert eine bestimmte Dateinamenerweiterung. Allerdings ist eine Erweiterung der "trägt" verwendet, wenn Sie keine Dateinamenerweiterung angeben.  
  
## <a name="example"></a>Beispiel  
 Die folgende Befehlszeile führt eine vorverarbeitung PROGRAM.cpp, behält Kommentare, fügt [#line](../../preprocessor/hash-line-directive-c-cpp.md) Direktiven und das Ergebnis in der Datei MYPROCESS.i schreibt.  
  
```  
CL /P /FiMYPROCESS.I PROGRAM.CPP  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [/ P (vorverarbeitung in eine Datei)](../../build/reference/p-preprocess-to-a-file.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)