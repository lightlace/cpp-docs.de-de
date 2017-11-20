---
title: VERSION (C/C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VERSION
dev_langs: C++
helpviewer_keywords: VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 059f3bda040257ab58412360cdfbac20869e381d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="version-cc"></a>VERSION (C/C++)
Teilt LINK, um eine Zahl im Header der .exe-Datei zu speichern oder die DLL.  
  
```  
VERSION major[.minor]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die *wichtigen* und *kleinere* Argumente sind Dezimalzahlen im Bereich von 0 bis 65.535. Der Standardwert ist 0,0-Version.  
  
 Eine entsprechende Möglichkeit, geben Sie eine Versionsnummer wird mit der [Versionsinformationen](../../build/reference/version-version-information.md) (/ VERSION) Option.  
  
## <a name="see-also"></a>Siehe auch  
 [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)