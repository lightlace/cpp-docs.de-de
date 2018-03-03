---
title: VCPROFILE_PATH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VCPROFILE_PATH
dev_langs:
- C++
helpviewer_keywords:
- VCPROFILE_PATH environment variable
ms.assetid: 25217aa4-7e86-4eba-854d-10b3c457e4df
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea682b70f4417ef49bfca530af5f12f21699a389
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="vcprofilepath"></a>VCPROFILE_PATH
Geben Sie das Verzeichnis aus, um die PGC-Dateien zu erstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
VCPROFILE_PATH=path  
```  
  
#### <a name="parameters"></a>Parameter  
 `path`  
 Der Verzeichnispfad, in den PGC-Dateien hinzugefügt werden.  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig werden PGC-Dateien im selben Verzeichnis wie die Binärdatei profilierten erstellt.  Wenn der absolute Pfad der Binärdatei nicht vorhanden ist wie die Groß-/Kleinschreibung möglicherweise beim Ausführen von Profilszenarien auf einem anderen Computer aus, in denen die Binärdatei erstellt wurde, Sie können jedoch festlegen `VCPROFILE_PATH` auf einen Pfad, der vorhanden ist.  
  
## <a name="example"></a>Beispiel  
  
```  
set VCPROFILE_PATH=c:\  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Umgebungsvariablen für profilgesteuerte Optimierungen](../../build/reference/environment-variables-for-profile-guided-optimizations.md)