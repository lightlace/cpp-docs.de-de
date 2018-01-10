---
title: -APPCONTAINER | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /APPCONTAINER
dev_langs: C++
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 19e926cbfd1fc58e04c8370825dd83eacff05dfe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="appcontainer"></a>/APPCONTAINER
Markiert eine ausführbare Datei, die in einem App-Container ausgeführt werden muss, z. B. eine [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] - oder UWP-App (universelle Windows-Plattform).  
  
```  
  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 Eine ausführbare Datei, bei der die **/APPCONTAINER** -Option festgelegt wurde, kann nur in einem App-Container ausgeführt werden. Das ist die in Windows 8 eingeführte Prozessisolationsumgebung. Für [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] - und UWP-Apps muss diese Option festgelegt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [EDITBIN-Optionen](../../build/reference/editbin-options.md)   
 [Was ist eine universelle Windows-App?](http://go.microsoft.com/fwlink/p/?LinkID=522074)