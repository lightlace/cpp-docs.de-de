---
title: CDefaultCharTraits Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 24aa01ec29f063c1fa65ebe24c707deb1ea58556
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361726"
---
# <a name="cdefaultchartraits-class"></a>CDefaultCharTraits-Klasse
Diese Klasse enthält zwei statische Funktionen zum Konvertieren von Zeichen zwischen Groß- und Kleinbuchstaben.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T>  
class CDefaultCharTraits
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der Daten in der Auflistung gespeichert werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDefaultCharTraits::CharToLower](#chartolower)|(Statisch) Mit dieser Funktion können ein Zeichen in Großbuchstaben zu konvertieren.|  
|[CDefaultCharTraits::CharToUpper](#chartoupper)|(Statisch) Mit dieser Funktion können ein Zeichen in Kleinbuchstaben konvertiert.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse bietet Funktionen, die von der Klasse ausgelastet sind [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="chartolower"></a>  CDefaultCharTraits::CharToLower  
 Mit dieser Funktion können ein Zeichen in Kleinbuchstaben konvertiert.  
  
```
static wchar_t CharToLower(wchar_t x);  
static char CharToLower(char x);
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Das Zeichen in Kleinbuchstaben konvertiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]  
  
##  <a name="chartoupper"></a>  CDefaultCharTraits::CharToUpper  
 Mit dieser Funktion können ein Zeichen in Großbuchstaben zu konvertieren.  
  
```
static wchar_t CharToUpper(wchar_t x);  
static char CharToUpper(char x);
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 Das Zeichen in Großbuchstaben zu konvertieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
