---
title: Rename_namespace | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rename_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7608255b5369443ce1045f896b776cb283fdb1cb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411858"
---
# <a name="renamenamespace"></a>rename_namespace
**C++-spezifisch**  
  
Benennt den Namespace, der die Inhalte der Typbibliothek enthält, um.  
  
## <a name="syntax"></a>Syntax  
  
```  
rename_namespace("NewName")  
```  
  
### <a name="parameters"></a>Parameter  
*Neuer Name*  
Der neue Name des neuen Namespace.  
  
## <a name="remarks"></a>Hinweise  
 
Es dauert ein einzelnes Argument, *NewName*, die den neuen Namen für den Namespace angibt.  
  
Verwenden Sie zum Entfernen des Namespaces der [No_namespace](../preprocessor/no-namespace.md) Attribut.  
  
**Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)