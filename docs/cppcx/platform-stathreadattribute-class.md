---
title: 'Platform:: STAThreadAttribute-Klasse | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Platform
- COLLECTION/Platform::Platform::STAThreadAttribute constructor 1
- COLLECTION/Platform::Platform::STAThreadAttribute::Equals
- COLLECTION/Platform::Platform::STAThreadAttribute::GetHashCode
- COLLECTION/Platform::Platform::STAThreadAttribute::ToString
dev_langs:
- C++
helpviewer_keywords:
- Platform::STAThreadAttribute Class
ms.assetid: f97960fc-e673-4d9e-910a-54c8415411c4
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab58409bf86af77c9b1f751b9978b5e7103bd043
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="platformstathreadattribute-class"></a>Platform::STAThreadAttribute-Klasse
Legt Singlethreaded Apartment (STA) als Threadingmodell für Anwendungen fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
public ref class STAThreadAttribute sealed : Attribute  
```  
  
### <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[STAThreadAttribute-Konstruktor 1](#ctor)|Initialisiert eine neue Instanz der Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
 Das STAThreadAttribute-Attribut erbt von [Platform:: Object-Klasse](../cppcx/platform-object-class.md). „STAThreadAttribute“ wird zudem überladen oder weist die folgenden Member auf:  
  
|name|Beschreibung|  
|----------|-----------------|  
|[STAThreadAttribute::Equals](#equals)|Bestimmt, ob das angegebene Objekt mit dem aktuellen Objekt identisch ist.|  
|[STAThreadAttribute::GetHashCode](#gethashcode)|Gibt den Hashcode für diese Instanz zurück.|  
|[STAThreadAttribute::ToString](#tostring)|Gibt eine Zeichenfolge zurück, die das aktuelle Objekt darstellt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Platform`  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform  



## <a name="ctor"></a> STAThreadAttribute constructor
Initialisiert eine neue Instanz der STAThreadAttribute-Klasse.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
public:STAThreadAttribute()  
```  
  


## <a name="equals"></a> STAThreadAttribute::Equals
Bestimmt, ob das angegebene Objekt mit dem aktuellen Objekt identisch ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
public:virtual override bool Equals(  Object^ obj)  
```  
  
### <a name="parameters"></a>Parameter  
 obj  
 Das zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Objekte gleich sind, andernfalls `false`.  
  


## <a name="gethashcode"></a> STAThreadAttribute::GetHashCode
Gibt den Hashcode für diese Instanz zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
public:int GetHashCode()  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Hashcode für diese Instanz.  
  


## <a name="tostring"></a> STAThreadAttribute::ToString
Gibt eine Zeichenfolge zurück, die das aktuelle Objekt darstellt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
public:String^ ToString()  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die das aktuelle Objekt darstellt.  
  

  
## <a name="see-also"></a>Siehe auch  
 [Platform-Namespace](platform-namespace-c-cx.md)