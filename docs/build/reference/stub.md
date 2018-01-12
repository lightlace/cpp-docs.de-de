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
ms.workload: cplusplus
ms.openlocfilehash: 58430f8211f8859b65103b53d1f98a173c4635ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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