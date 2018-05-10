---
title: samplerklasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- sampler
- AMP_GRAPHICS/sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::get_address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::get_border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::get_filter_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::filter_mode
dev_langs:
- C++
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f9788b62385f7c6f5eb82e3fbc69d63d3120cc2
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="sampler-class"></a>Samplerklasse
Die Samplerklasse aggregiert Informationen für die Samplingkonfiguration, die für das Textursampling verwendet werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class sampler;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Sampler-Konstruktor](#ctor)|Überladen. Erstellt eine Samplerinstanz.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[get_address_mode](#get_address_mode)|Gibt das `address_mode`-Objekt zurück, das mit dem Samplerobjekt verknüpft ist.|  
|[get_border_color](#get_border_color)|Gibt die Rahmenfarbe zurück, die dem Samplerobjekt verknüpft ist.|  
|[get_filter_mode](#get_filter_mode)|Gibt das `filter_mode`-Objekt zurück, das mit dem Samplerobjekt verknüpft ist.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator=](#operator_eq)|Überladen. Zuweisungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[address_mode](#address_mode)|Ruft den Adressmodus des `sampler`-Objekts ab.|  
|[border_color](#border_color)|Legt die Rahmenfarbe des `sampler`-Objekts fest.|  
|[filter_mode](#filter_mode)|Ruft den Filtermodus des `sampler`-Objekts ab.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `sampler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp_graphics.h  
  
 **Namespace:** Concurrency:: Graphics  
  
##  <a name="ctor"></a> Sampler 

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
  
##  <a name="address_mode"></a> address_mode 

 Ruft den Adressmodus des `sampler`-Objekts ab.  
  
```  
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;  
```  
  
##  <a name="border_color"></a> border_color 

 Legt die Rahmenfarbe des `sampler`-Objekts fest.  
  
```  
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;  
```  
  
##  <a name="filter_mode"></a> filter_mode 

 Ruft den Filtermodus des `sampler`-Objekts ab.  
  
```  
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;  
```  
  
##  <a name="get_address_mode"></a> get_address_mode 

 Gibt den Filtermodus zurück, der für dieses `sampler`-Objekt konfiguriert ist.  
  
```  
Concurrency::graphics::address_mode get_address_mode() const __GPU;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Adressmodus, der für den Sampler konfiguriert ist.  
  
##  <a name="get_border_color"></a> get_border_color 

 Gibt die Rahmenfarbe zurück, die für dieses `sampler`-Objekt konfiguriert ist.  
  
```  
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein float_4-Objekt, das die Rahmenfarbe enthält.  
  
##  <a name="get_filter_mode"></a> get_filter_mode 

 Gibt den Filtermodus zurück, der für dieses `sampler`-Objekt konfiguriert ist.  
  
```  
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Filtermodus, der für den Sampler konfiguriert ist.  
  
##  <a name="operator_eq"></a> Operator = 

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
 [Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
