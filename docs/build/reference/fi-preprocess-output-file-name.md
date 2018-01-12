---
title: -Fi (Ausgabedateiname vorverarbeiten) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Fi
dev_langs: C++
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9bc3076a529984358aed16902f509ceb01423f9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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