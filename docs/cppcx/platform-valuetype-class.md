---
title: 'Platform:: ValueType-Klasse | Microsoft Docs'
ms.custom: 
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::ValueType::ToString
dev_langs: C++
helpviewer_keywords: Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4dba418e74affb2531e3ebbd43d95c35601e9a26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="platformvaluetype-class"></a>Platform::ValueType-Klasse
Die Basisklasse für Instanzen von Werttypen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
public ref class ValueType : Object  
```  
  
## <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|[ValueType::ToString](#tostring)|Gibt eine Zeichenfolgendarstellung des Objekts zurück. Geerbt von [Platform:: Object](../cppcx/platform-object-class.md).|  
  
### <a name="remarks"></a>Hinweise  
 Die ValueType-Klasse wird zum Erstellen von Werttypen verwendet. „ValueType“ ist von „Object“ abgeleitet, die über Basismember verfügt. Der Compiler trennt jedoch diese Basismember von den Werttypen, die aus der ValueType-Klasse abgeleitet sind. Der Compiler fügt die Basismember wieder an, wenn ein Werttyp mittels Boxing konvertiert wird.  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client:** Windows 8  
  
 **Unterstützter Server:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  

## <a name="tostring"></a>ValueType::ToString-Methode
Gibt eine Zeichenfolgendarstellung des Objekts zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
Platform::String ToString();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Platform:: String-Wert, der den Wert darstellt.  
    
## <a name="see-also"></a>Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)