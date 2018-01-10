---
title: 'Platform:: iboxarray-Schnittstelle | Microsoft Docs'
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
dev_langs: C++
helpviewer_keywords: Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 421f8517b8a96c40bb44dd959eba90b1bf903113
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="platformiboxarray-interface"></a>Platform::IBoxArray-Schnittstelle
,`IBoxArray` ist der Wrapper für Arrays von Werttypen, die über die Anwendungsbinärdateischnittstelle (ABI) übergeben werden oder in Auflistungen von `Platform::Object^` -Elementen, wie die in XAML-Steuerelementen, gespeichert werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template <typename T>  
interface class IBoxArray  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ des geschachtelten Werts in jedem Arrayelement.  
  
### <a name="remarks"></a>Hinweise  
 `IBoxArray`ist die C + c++ / CX-Namen für `Windows::Foundation::IReferenceArray`.  
  
### <a name="members"></a>Member  
 Die `IBoxArray` -Schnittstelle erbt von der `IValueType` -Schnittstelle. `IBoxArray` umfasst auch folgende Member:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Wert](#value)|Gibt das nicht geschachtelte Array zurück, das zuvor in dieser `IBoxArray` -Instanz gespeichert wurde.|  

## <a name="value"></a>Iboxarray:: Value-Eigenschaft
Gibt den ursprünglich in diesem Objekt gespeicherten Wert zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
property T Value {T get();}  
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ des geschachtelten Werts.  
  
### <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Gibt den ursprünglich in diesem Objekt gespeicherten Wert zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ein Beispiel finden Sie unter [Boxing](../cppcx/boxing-c-cx.md).  
  
  
## <a name="see-also"></a>Siehe auch  
 [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)