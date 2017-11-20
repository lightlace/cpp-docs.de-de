---
title: STUB | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: STUB
dev_langs: C++
helpviewer_keywords: STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 27d7ee77d527e8d8715d182609f1cb847b10a3d4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="stub"></a>STUB
Wenn eine Moduldefinitionsdatei verwendet, die einen virtuellen Gerätetreiber (VxD) erstellt, können Sie einen Dateinamen angeben, die eine Anweisung-Struktur (definiert in WINNT. H), in dem virtuelle Gerätetreiber (VxD), anstatt das Standardheader verwendet werden.  
  
```  
STUB:filename  
```  
  
## <a name="remarks"></a>Hinweise  
 Alternativ können Sie angeben *Filename* ist mit der [/STUB](../../build/reference/stub-ms-dos-stub-file-name.md) (Linkeroption).  
  
 STUB ist in einer Moduldefinitionsdatei nur beim Erstellen eines VxD gültig.  
  
## <a name="see-also"></a>Siehe auch  
 [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)