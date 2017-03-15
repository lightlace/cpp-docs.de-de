---
title: Klasse CDefaultCharTraits | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultCharTraits
- ATL::CDefaultCharTraits<T>
- ATL.CDefaultCharTraits
- ATL.CDefaultCharTraits<T>
- ATL::CDefaultCharTraits
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 12991cfcf1ac96808a0315899d01ce3012324dc6
ms.lasthandoff: 02/24/2017

---
# <a name="cdefaultchartraits-class"></a>CDefaultCharTraits-Klasse
Diese Klasse stellt zwei statische Funktionen zum Konvertieren von Zeichen zwischen Groß- und Kleinschreibung.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T>  
class CDefaultCharTraits
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der Daten in der Auflistung gespeichert werden.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDefaultCharTraits::CharToLower](#chartolower)|(Statisch) Rufen Sie diese Funktion, um ein Zeichen in Großbuchstaben zu konvertieren.|  
|[CDefaultCharTraits::CharToUpper](#chartoupper)|(Statisch) Rufen Sie diese Funktion, um ein Zeichen in Kleinbuchstaben zu konvertieren.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse bietet Funktionen, die von der Klasse verwendet werden [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="a-namechartolowera--cdefaultchartraitschartolower"></a><a name="chartolower"></a>CDefaultCharTraits::CharToLower  
 Rufen Sie diese Funktion, um ein Zeichen in Kleinbuchstaben zu konvertieren.  
  
```
static wchar_t CharToLower(wchar_t x);  
static char CharToLower(char x);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Das Zeichen in Kleinbuchstaben konvertiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#132;](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]  
  
##  <a name="a-namechartouppera--cdefaultchartraitschartoupper"></a><a name="chartoupper"></a>CDefaultCharTraits::CharToUpper  
 Rufen Sie diese Funktion, um ein Zeichen in Großbuchstaben zu konvertieren.  
  
```
static wchar_t CharToUpper(wchar_t x);  
static char CharToUpper(char x);
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 Das Zeichen in Großbuchstaben zu konvertieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

