---
title: 'Platform:: MTAThreadAttribute-Klasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::MTAThreadAttribute::Equals
- VCCORLIB/Platform::MTAThreadAttribute::GetHashCode
- VCCORLIB/Platform::MTAThreadAttribute::ToString
dev_langs:
- C++
helpviewer_keywords:
- Platform::MTAThreadAttribute Class
ms.assetid: bfc546a7-4333-4407-85b4-4721565e1f44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 389767cdbd09cb5a2139b9302fc25fe02fb8a056
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757119"
---
# <a name="platformmtathreadattribute-class"></a>Platform::MTAThreadAttribute-Klasse
Legt Multithreaded Apartment (MTA) als Threadingmodell für Anwendungen fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
public ref class MTAThreadAttribute sealed : Attribute  
```  
  
### <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[MTAThreadAttribute-Konstruktor 1](#ctor) Konstruktor|Initialisiert eine neue Instanz der Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
 Das MTAThreadAttribute-Attribut erbt von [Platform:: Object Class](../cppcx/platform-object-class.md). „MTAThreadAttribute“ wird zudem überladen oder weist die folgenden Member auf:  
  
|name|Beschreibung|  
|----------|-----------------|  
|[MTAThreadAttribute::Equals](#equals)|Bestimmt, ob das angegebene Objekt mit dem aktuellen Objekt identisch ist.|  
|[MTAThreadAttribute::GetHashCode](#gethashcode)|Gibt den Hashcode für diese Instanz zurück.|  
|[MTAThreadAttribute::ToString](#tostring)|Gibt eine Zeichenfolge zurück, die das aktuelle Objekt darstellt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Platform`  
  
### <a name="requirements"></a>Anforderungen  
 **Metadaten:** platform.winmd  
  
 **Namespace:** Platform  



## <a name="ctor"></a> MTAThreadAttribute-Konstruktor
Initialisiert eine neue Instanz der MTAThreadAttribute-Klasse.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
public:MTAThreadAttribute()  
```  
  


## <a name="equals"></a> MTAThreadAttribute::Equals
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
  


## <a name="gethashcode"></a> MTAThreadAttribute::GetHashCode
Gibt den Hashcode für diese Instanz zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
public:int GetHashCode()  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Hashcode für diese Instanz.  
  


## <a name="tostring"></a> MTAThreadAttribute::ToString
Gibt eine Zeichenfolge zurück, die das aktuelle Objekt darstellt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
public:String^ ToString()  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die das aktuelle Objekt darstellt.  
    
## <a name="see-also"></a>Siehe auch  
 [Plattform-Namespace](platform-namespace-c-cx.md)