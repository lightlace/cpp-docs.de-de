---
title: VERSION (C/C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VERSION
dev_langs:
- C++
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fcaf4e113af6182a2d3d735e4c668b62336e2c79
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375021"
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