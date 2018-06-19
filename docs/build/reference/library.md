---
title: BIBLIOTHEK | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- LIBRARY
dev_langs:
- C++
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d2fb7e69b0557bf96601666c390b3d59412b5a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371163"
---
# <a name="library"></a>LIBRARY
Gibt LINK zu eine DLL zu erstellen. Zur gleichen Zeit erstellt LINK eine Importbibliothek, es sei denn, eine .exp-Datei in den Build verwendet wird.  
  
```  
LIBRARY [library][BASE=address]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die *Bibliothek* Argument gibt den Namen der DLL. Sie können auch die [/OUT](../../build/reference/out-output-file-name.md) Linkeroption, um die DLL Ausgabeordner angegeben.  
  
 Der BASE =*Adresse* Argument legt die Basisadresse, die das Betriebssystem verwendet wird, um die DLL zu laden. Dieses Argument überschreibt das Standardverzeichnis für die DLL des 0 x 10000000. Siehe dazu die Beschreibung der [/BASE](../../build/reference/base-base-address.md) Option ausführliche Informationen über Basisadressen.  
  
 Denken Sie daran, verwenden Sie die [/DLL](../../build/reference/dll-build-a-dll.md) (Linkeroption), wenn Sie eine DLL erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)