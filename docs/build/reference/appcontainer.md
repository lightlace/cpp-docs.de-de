---
title: -APPCONTAINER | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /APPCONTAINER
dev_langs:
- C++
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c47154d7a5eddd26573612708462c0352da30ae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="appcontainer"></a>/APPCONTAINER
Kennzeichnet eine ausführbare Datei, die in einem app-Container ausgeführt werden muss, z. B. eine Microsoft-Store- oder universellen Windows-app.  
  
```  
  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 Eine ausführbare Datei, bei der die **/APPCONTAINER** -Option festgelegt wurde, kann nur in einem App-Container ausgeführt werden. Das ist die in Windows 8 eingeführte Prozessisolationsumgebung. Bei Microsoft Store und universelle Windows-apps muss diese Option festgelegt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [EDITBIN-Optionen](../../build/reference/editbin-options.md)   
 [Was ist eine universelle Windows-App?](http://go.microsoft.com/fwlink/p/?LinkID=522074)