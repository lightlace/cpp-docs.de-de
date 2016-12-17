---
title: "/APPCONTAINER"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/APPCONTAINER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/APPCONTAINER editbin-Option"
  - "APPCONTAINER editbin-Option"
  - "-APPCONTAINER editbin-Option"
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# /APPCONTAINER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Markiert eine ausführbare Datei, die in einem App\-Container ausgeführt werden muss, z. B. eine [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\- oder UWP\-App \(universelle Windows\-Plattform\).  
  
```  
  
/APPCONTAINER[:NO]  
```  
  
## Hinweise  
 Eine ausführbare Datei, bei der die **\/APPCONTAINER**\-Option festgelegt wurde, kann nur in einem App\-Container ausgeführt werden. Das ist die in Windows 8 eingeführte Prozessisolationsumgebung. Für [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\- und UWP\-Apps muss diese Option festgelegt werden.  
  
## Siehe auch  
 [EDITBIN\-Optionen](../../build/reference/editbin-options.md)   
 [Was ist eine universelle Windows\-App?](http://go.microsoft.com/fwlink/p/?LinkID=522074)