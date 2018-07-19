---
title: CW2WEX-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CW2WEX
- ATLCONV/ATL::CW2WEX
- ATLCONV/ATL::CW2WEX::CW2WEX
- ATLCONV/ATL::CW2WEX::m_psz
- ATLCONV/ATL::CW2WEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CW2WEX class
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7710856f05204dbbbc2bc15e2e62056123cd85cc
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884073"
---
# <a name="cw2wex-class"></a>CW2WEX-Klasse
Diese Klasse wird von der Zeichenfolgen-konvertierungsmakros CW2TEX und CT2WEX und der Typedef CW2W verwendet.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <int t_nBufferLength = 128>  
class CW2WEX
```  
  
#### <a name="parameters"></a>Parameter  
 *t_nBufferLength*  
 Die Größe des Puffers, die in der Übersetzungsprozess verwendet werden soll. Die Standardeinstellung ist 128 Bytes.  
  
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
|[CW2WEX::m_psz](#m_psz)|Der Datenmember, die die Quellzeichenfolge speichert.|  
|[CW2WEX::m_szBuffer](#m_szbuffer)|Die statischen Puffer, der zum Speichern der konvertierten Zeichenfolge.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn zusätzliche Funktionalität erforderlich ist, verwenden Sie in Ihrem Code CW2TEX, CT2WEX oder CW2W an.  
  
 Diese Klasse enthält einen statischen Puffer mit fester Größe, mit der das Ergebnis der Konvertierung zu speichern. Wenn das Ergebnis zu groß, um in den statischen Puffer zu passen, weist die Klasse Speicher verwenden **Malloc**, den Speicher freigibt, wenn das Objekt den Gültigkeitsbereich verlässt. Dadurch wird sichergestellt, dass im Gegensatz zu Text konvertierungsmakros, die in früheren Versionen von ATL, dieser Klasse sicher in Schleifen verwendet werden kann und es der Stack overflow wird nicht verfügbar.  
  
 Wenn die Klasse versucht, die speicherbelegung auf dem Heap und ein Fehler auftritt, ruft sie `AtlThrow` mit einem Argument von E_OUTOFMEMORY.  
  
 Standardmäßig verwenden die ATL-konvertierungsklassen und-Makros ANSI-Codepage des aktuellen Threads für die Konvertierung.  
  
 Die folgenden Makros basieren auf diese Klasse:  
  
- CW2TEX  
  
- CT2WEX  
  
 Die folgende Typedef basiert auf diese Klasse:  
  
- CW2W  
  
 Eine Erläuterung der diese textkonvertierungsmakros, finden Sie unter [ATL- und MFC-Zeichenfolgen-Konvertierungsmakros](string-conversion-macros.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [ATL- und MFC-Zeichenfolgen-Konvertierungsmakros](string-conversion-macros.md) für ein Beispiel für diese Zeichenfolgen-konvertierungsmakros.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlconv.h  
  
##  <a name="cw2wex"></a>  CW2WEX::CW2WEX  
 Der Konstruktor.  
  
```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *psz*  
 Die Textzeichenfolge, die konvertiert werden.  
  
 *nCodePage*  
 Die Codepage. In dieser Klasse verwendet nicht.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt den Puffer für die Übersetzung erforderlich sind.  
  
##  <a name="dtor"></a>  CW2WEX:: ~ CW2WEX  
 Der Destruktor...  
  
```
~CW2WEX() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt den zugeordneten Puffer frei.  
  
##  <a name="m_psz"></a>  CW2WEX::m_psz  
 Der Datenmember, die die Quellzeichenfolge speichert.  
  
```
LPWSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>  CW2WEX::m_szBuffer  
 Die statischen Puffer, der zum Speichern der konvertierten Zeichenfolge.  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpwstr"></a>  CW2WEX::Operator LPWSTR  
 CAST-Operator.  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Zeichenfolge, LPWSTR eingeben.  
  
## <a name="see-also"></a>Siehe auch  
 [CA2AEX-Klasse](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX-Klasse](../../atl/reference/ca2caex-class.md)   
 [CA2WEX-Klasse](../../atl/reference/ca2wex-class.md)   
 [CW2AEX-Klasse](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX-Klasse](../../atl/reference/cw2cwex-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
