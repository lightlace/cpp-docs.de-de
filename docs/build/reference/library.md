---
title: BIBLIOTHEK | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LIBRARY
dev_langs: C++
helpviewer_keywords: LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 75f337f563707a1ab2b1dabe0042b678c03172e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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