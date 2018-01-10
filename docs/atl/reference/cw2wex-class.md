---
title: CW2WEX Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CW2WEX
- ATLCONV/ATL::CW2WEX
- ATLCONV/ATL::CW2WEX::CW2WEX
- ATLCONV/ATL::CW2WEX::m_psz
- ATLCONV/ATL::CW2WEX::m_szBuffer
dev_langs: C++
helpviewer_keywords: CW2WEX class
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c35439b1309e75359177cf45ade4c6be9459f623
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cw2wex-class"></a>CW2WEX-Klasse
Diese Klasse wird verwendet, indem die Makros zur zeichenfolgenkonvertierung `CW2TEX` und `CT2WEX`, und die Typedef `CW2W`.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <int t_nBufferLength = 128>  
class CW2WEX
```  
  
#### <a name="parameters"></a>Parameter  
 `t_nBufferLength`  
 Die Größe des Puffers, der bei der Übersetzung verwendet werden soll. Die Standardlänge beträgt 128 Bytes.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CW2WEX::CW2WEX](#cw2wex)|Der Konstruktor.|  
|[CW2WEX:: ~ CW2WEX](#dtor)|Der Destruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CW2WEX::Operator LPWSTR](#operator_lpwstr)|Konvertierungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CW2WEX::m_psz](#m_psz)|Das Datenelement, das die Quellzeichenfolge speichert.|  
|[CW2WEX::m_szBuffer](#m_szbuffer)|Den statischen Puffer zum Speichern der konvertierten Zeichenfolge verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn zusätzlicher Funktionalität erforderlich ist, verwenden Sie `CW2TEX`, `CT2WEX`, oder `CW2W` im Code.  
  
 Diese Klasse enthält einen statischen Puffer mit fester Größe, mit der das Ergebnis der Konvertierung zu speichern. Wenn das Ergebnis zu groß ist, um in den statischen Puffer zu passen, weist die Klasse mittels `malloc` Arbeitsspeicher zu und gibt den Speicher wieder frei, wenn das Objekt sich nicht mehr im Gültigkeitsbereich befindet. Dadurch wird sichergestellt, dass im Gegensatz zu Text konvertierungsmakros, die in früheren Versionen von ATL, diese Klasse sicher in Schleifen verwendet werden kann, sodass er den Stapel "Überlauf" wird nicht verfügbar.  
  
 Wenn die Klasse versucht, Zuweisen von Arbeitsspeicher auf dem Heap und ein Fehler auftritt, er ruft `AtlThrow` mit dem Argument **E_OUTOFMEMORY**.  
  
 Standardmäßig verwenden die ATL-konvertierungsklassen und-Makros ANSI-Codepage für den aktuellen Thread für die Konvertierung.  
  
 Die folgenden Makros hängen von dieser Klasse:  
  
- `CW2TEX`  
  
- `CT2WEX`  
  
 Die folgenden Typedef basiert auf diese Klasse:  
  
- `CW2W`  
  
 Eine Erläuterung der diese textkonvertierungsmakros, finden Sie unter [ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](string-conversion-macros.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](string-conversion-macros.md) für ein Beispiel zur Verwendung dieser Makros zur zeichenfolgenkonvertierung.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlconv.h  
  
##  <a name="cw2wex"></a>CW2WEX::CW2WEX  
 Der Konstruktor.  
  
```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die Textzeichenfolge, die konvertiert werden.  
  
 `nCodePage`  
 Die Codepage. In dieser Klasse verwendet nicht.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt den Puffer für die Übersetzung erforderlich.  
  
##  <a name="dtor"></a>CW2WEX:: ~ CW2WEX  
 Der Destruktor...  
  
```
~CW2WEX() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt den zugeordneten Puffer frei.  
  
##  <a name="m_psz"></a>CW2WEX::m_psz  
 Das Datenelement, das die Quellzeichenfolge speichert.  
  
```
LPWSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>CW2WEX::m_szBuffer  
 Den statischen Puffer zum Speichern der konvertierten Zeichenfolge verwendet.  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpwstr"></a>CW2WEX::Operator LPWSTR  
 Umwandlungsoperator.  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Zeichenfolge als Typ `LPWSTR`.  
  
## <a name="see-also"></a>Siehe auch  
 [CA2AEX-Klasse](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX-Klasse](../../atl/reference/ca2caex-class.md)   
 [CA2WEX-Klasse](../../atl/reference/ca2wex-class.md)   
 [CW2AEX-Klasse](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX-Klasse](../../atl/reference/cw2cwex-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
