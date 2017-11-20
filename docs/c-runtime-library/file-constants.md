---
title: Dateikonstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _O_EXCL
- _O_RDWR
- _O_APPEND
- _O_RDONLY
- _O_TRUNC
- _O_CREAT
- _O_WRONLY
dev_langs: C++
helpviewer_keywords:
- _O_RDWR constant
- O_EXCL constant
- O_RDWR constant
- O_WRONLY constant
- O_APPEND constant
- O_CREAT constant
- _O_CREAT constant
- _O_APPEND constant
- _O_EXCL constant
- O_TRUNC constant
- _O_RDONLY constant
- _O_TRUNC constant
- O_RDONLY constant
- _O_WRONLY constant
ms.assetid: c8fa5548-9ac2-4217-801d-eb45e86f2fa4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 51d5de22dce0b68c55fc928b1a251b30d9ceed7f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="file-constants"></a>Dateikonstanten
## <a name="syntax"></a>Syntax  
  
```  
  
#include <fcntl.h>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Der aus einer oder mehreren der folgenden Konstanten gebildete Ganzzahlausdruck bestimmt den Typ der durchführbaren Lese- oder Schreibvorgänge. Er wird durch Kombination einer oder mehrerer Konstanten mit einer Übersetzungsmoduskonstanten gebildet.  
  
 Die Dateikonstanten lauten wie folgt:  
  
 `_O_APPEND`  
 Positioniert den Dateizeiger vor jedem Schreibvorgang am Ende einer Datei.  
  
 `_O_CREAT`  
 Erstellt und öffnet eine neue Datei zum Schreiben. Dies hat keine Auswirkungen, wenn die durch *filename* angegebene Datei vorhanden ist.  
  
 `_O_EXCL`  
 Gibt einen Fehlerwert zurück, wenn die durch *filename* angegebene Datei vorhanden ist. Gilt nur bei Verwendung mit `_O_CREAT`.  
  
 `_O_RDONLY`  
 Die Datei wird nur zum Lesen geöffnet. Wenn dieses Flag angegeben ist, kann weder `_O_RDWR` noch `_O_WRONLY` angegeben werden.  
  
 `_O_RDWR`  
 Die Datei wird zum Lesen und Schreiben geöffnet. Wenn dieses Flag angegeben ist, kann weder `_O_RDONLY` noch `_O_WRONLY` angegeben werden.  
  
 `_O_TRUNC`  
 Öffnet eine vorhandene Datei und verkürzt sie auf die Länge 0 (null). Für die Datei muss eine Schreibberechtigung bestehen. Der Inhalt der Datei ist zerstört. Wenn dieses Flag angegeben ist, können Sie `_O_RDONLY` nicht angeben.  
  
 `_O_WRONLY`  
 Die Datei wird nur zum Schreiben geöffnet. Wenn dieses Flag angegeben ist, kann weder `_O_RDONLY` noch `_O_RDWR` angegeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [_open, _wopen](../c-runtime-library/reference/open-wopen.md)   
 [_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)