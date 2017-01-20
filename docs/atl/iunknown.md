---
title: "IUnknown"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM-Schnittstellen, base interface"
  - "IUnknown interface"
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# IUnknown
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) ist die Basisschnittstelle jeder zweiten COM\-Schnittstelle.  Diese Schnittstelle definiert drei Methoden: [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521), [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317).  [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) ermöglicht einem Schnittstellenbenutzer, vom Objekt einen Zeiger zu einer seiner anderen Schnittstellen anzufordern.  [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) implementieren die Verweiszählung für die Schnittstelle.  
  
## Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [IUnknown and Interface Inheritance](http://msdn.microsoft.com/library/windows/desktop/ms692713)