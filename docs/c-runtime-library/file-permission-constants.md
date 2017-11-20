---
title: Dateiberechtigungskonstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _S_IWRITE
- _S_IREAD
dev_langs: C++
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aa42ebf645c737ffe2f5db9647a3ba3912669b27
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="file-permission-constants"></a>Dateiberechtigungskonstanten
## <a name="syntax"></a>Syntax  
  
```  
  
#include <sys/stat.h>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Eine der folgenden Konstanten ist erforderlich, wenn `_O_CREAT` (`_open`, `_sopen`) angegeben wird.  
  
 Das `pmode`-Argument gibt die Dateiberechtigungseinstellungen wie folgt an.  
  
|Konstante|Bedeutung|  
|--------------|-------------|  
|`_S_IREAD`|Lesen erlaubt|  
|`_S_IWRITE`|Schreiben erlaubt|  
|`_S_IREAD` &#124; `_S_IWRITE`|Lesen und Schreiben erlaubt|  
  
 Bei Verwendung als `pmode`-Argument für `_umask` legt die Manifestkonstante die Berechtigungseinstellung wie folgt fest.  
  
|Konstante|Bedeutung|  
|--------------|-------------|  
|`_S_IREAD`|Schreiben nicht erlaubt (Datei ist schreibgeschützt)|  
|`_S_IWRITE`|Lesen nicht erlaubt (Datei ist lesegeschützt)|  
|`_S_IREAD` &#124; `_S_IWRITE`|Weder Lesen noch Schreiben erlaubt|  
  
## <a name="see-also"></a>Siehe auch  
 [_open, _wopen](../c-runtime-library/reference/open-wopen.md)   
 [_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [_umask](../c-runtime-library/reference/umask.md)   
 [Standardtypen](../c-runtime-library/standard-types.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)