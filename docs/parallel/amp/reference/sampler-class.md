---
title: samplerklasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 090e05e294646b7571a3d06ca8ed23583a306756
ms.lasthandoff: 02/24/2017

---
# <a name="sampler-class"></a>Samplerklasse
Die Samplerklasse aggregiert Informationen für die Samplingkonfiguration, die für das Textursampling verwendet werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class sampler;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Sampler-Konstruktor](#ctor)|Überladen. Erstellt eine Samplerinstanz.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Get_address_mode-Methode](#get_address_mode)|Gibt das `address_mode`-Objekt zurück, das mit dem Samplerobjekt verknüpft ist.|  
|[Get_border_color-Methode](#get_border_color)|Gibt die Rahmenfarbe zurück, die dem Samplerobjekt verknüpft ist.|  
|[Get_filter_mode-Methode](#get_filter_mode)|Gibt das `filter_mode`-Objekt zurück, das mit dem Samplerobjekt verknüpft ist.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator =-Operator](#operator_eq)|Überladen. Zuweisungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Address_mode-Datenmember](#address_mode)|Ruft den Adressmodus des `sampler`-Objekts ab.|  
|[Border_color-Datenmember](#border_color)|Legt die Rahmenfarbe des `sampler`-Objekts fest.|  
|[Filter_mode-Datenmember](#filter_mode)|Ruft den Filtermodus des `sampler`-Objekts ab.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `sampler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp_graphics.h  
  
 **Namespace:** Concurrency:: Graphics  
  
##  <a name="a-namectora-sampler"></a><a name="ctor"></a>Sampler 

 Erstellt eine Instanz der [samplerklasse](sampler-class.md).  
  
```  
sampler() restrict(cpu);

 *// [1] default constructor  
 
sampler(// [2] constructor  
    filter_mode _Filter_mode) restrict(cpu);

 
sampler(// [3] constructor  
    address_mode _Address_mode,  
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

 
sampler(// [4] constructor  
    filter_mode _Filter_mode,  
    address_mode _Address_mode,  
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

 
sampler(// [5] copy constructor  
    const sampler& _Other) restrict(amp,
    cpu);

 
sampler(// [6] move constructor  
    sampler&& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Filter_mode`  
 Der im Sampling verwendete Filtermodus.  
  
 `_Address_mode`  
 Die im Sampling für alle Dimensionen zu verwendenden Adressierung.  
  
 `_Border_color`  
 Die zu verwendenden Rahmenfarbe, wenn der Adressmodus address_border lautet. Der Standardwert ist `float_4(0.0f, 0.0f, 0.0f, 0.0f)`.  
  
 `_Other`  
 [5]-Kopierkonstruktor  
 Das `sampler`-Objekt, in das die neue `sampler`-Instanz kopiert werden soll.  
  
 [6]-bewegungskonstruktor  
 Das `sampler`-Objekt, das in die neue `sampler`-Instanz verschoben werden soll.  
  
##  <a name="a-nameaddressmodea-addressmode"></a><a name="address_mode"></a>address_mode 

 Ruft den Adressmodus des `sampler`-Objekts ab.  
  
```  
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;  
```  
  
##  <a name="a-namebordercolora-bordercolor"></a><a name="border_color"></a>border_color 

 Legt die Rahmenfarbe des `sampler`-Objekts fest.  
  
```  
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;  
```  
  
##  <a name="a-namefiltermodea-filtermode"></a><a name="filter_mode"></a>filter_mode 

 Ruft den Filtermodus des `sampler`-Objekts ab.  
  
```  
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;  
```  
  
##  <a name="a-namegetaddressmodea-getaddressmode"></a><a name="get_address_mode"></a>get_address_mode 

 Gibt den Filtermodus zurück, der für dieses `sampler`-Objekt konfiguriert ist.  
  
```  
Concurrency::graphics::address_mode get_address_mode() const __GPU;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Adressmodus, der für den Sampler konfiguriert ist.  
  
##  <a name="a-namegetbordercolora-getbordercolor"></a><a name="get_border_color"></a>get_border_color 

 Gibt die Rahmenfarbe zurück, die für dieses `sampler`-Objekt konfiguriert ist.  
  
```  
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein float_4-Objekt, das die Rahmenfarbe enthält.  
  
##  <a name="a-namegetfiltermodea-getfiltermode"></a><a name="get_filter_mode"></a>get_filter_mode 

 Gibt den Filtermodus zurück, der für dieses `sampler`-Objekt konfiguriert ist.  
  
```  
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Filtermodus, der für den Sampler konfiguriert ist.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>Operator = 

 Weist den Wert eines anderen Samplerobjekts einem vorhandenen Sampler zu.  
  
```  
sampler& operator= (// [1] copy assignment operator const sampler& _Other) restrict(amp,
    cpu);

 
sampler& operator= (// [2] move assingment operator sampler&& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 [1]-Kopierzuweisungsoperator  
 Das `sampler`-Objekt, das in dieses `sampler`-Objekt kopiert werden soll.  
  
 [2]-Bewegungszuweisungsoperator  
 Das `sampler`-Objekt, das in dieses `sampler`-Objekt verschoben werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf diese Samplerinstanz.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency:: Graphics-Namespace](concurrency-graphics-namespace.md)

