---
title: STUB | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- STUB
dev_langs:
- C++
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 385e073f877a938a3b73fa79036d27cf50c1e4ec
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375200"
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