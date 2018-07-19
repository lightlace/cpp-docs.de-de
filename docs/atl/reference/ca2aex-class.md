---
title: CA2AEX-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CA2AEX
- ATLCONV/ATL::CA2AEX
- ATLCONV/ATL::CA2AEX::CA2AEX
- ATLCONV/ATL::CA2AEX::m_psz
- ATLCONV/ATL::CA2AEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CA2AEX class
ms.assetid: 57dc65df-d9cf-4a84-99d3-6e031dde3664
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 94e9c33fb69b439cc6c99d87d00d24f60e87d780
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882129"
---
# <a name="ca2aex-class"></a>CA2AEX-Klasse
Diese Klasse wird von der Zeichenfolgen-konvertierungsmakros CA2TEX und CT2AEX und der Typedef CA2A verwendet.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <int t_nBufferLength = 128>
class CA2AEX
```  
  
#### <a name="parameters"></a>Parameter  
 *t_nBufferLength*  
 Die Größe des Puffers, die in der Übersetzungsprozess verwendet werden soll. Die Standardeinstellung ist 128 Bytes.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2AEX::CA2AEX](#ca2aex)|Der Konstruktor.|  
|[CA2AEX:: ~ CA2AEX](#dtor)|Der Destruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2AEX::Operator LPSTR](#operator_lpstr)|Konvertierungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2AEX::m_psz](#m_psz)|Der Datenmember, die die Quellzeichenfolge speichert.|  
|[CA2AEX::m_szBuffer](#m_szbuffer)|Die statischen Puffer, der zum Speichern der konvertierten Zeichenfolge.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn zusätzliche Funktionalität erforderlich ist, verwenden Sie in Ihrem eigenen Code CA2TEX, CT2AEX oder CA2A an.  
  
 Diese Klasse enthält einen statischen Puffer mit fester Größe, mit der das Ergebnis der Konvertierung zu speichern. Wenn das Ergebnis zu groß, um in den statischen Puffer zu passen, weist die Klasse Speicher verwenden **Malloc**, den Speicher freigibt, wenn das Objekt den Gültigkeitsbereich verlässt. Dadurch wird sichergestellt, dass im Gegensatz zu Text konvertierungsmakros, die in früheren Versionen von ATL, dieser Klasse sicher in Schleifen verwendet werden kann und es der Stack overflow wird nicht verfügbar.  
  
 Wenn die Klasse versucht, die speicherbelegung auf dem Heap und ein Fehler auftritt, ruft sie `AtlThrow` mit einem Argument von E_OUTOFMEMORY.  
  
 Standardmäßig verwenden die ATL-konvertierungsklassen und-Makros ANSI-Codepage des aktuellen Threads für die Konvertierung.  
  
 Die folgenden Makros basieren auf diese Klasse:  
  
- CA2TEX  
  
- CT2AEX  
  
 Die folgende Typedef basiert auf diese Klasse:  
  
- CA2A  
  
 Eine Erläuterung der diese textkonvertierungsmakros, finden Sie unter [ATL- und MFC-Zeichenfolgen-Konvertierungsmakros](string-conversion-macros.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [ATL- und MFC-Zeichenfolgen-Konvertierungsmakros](string-conversion-macros.md) für ein Beispiel für diese Zeichenfolgen-konvertierungsmakros.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlconv.h  
  
##  <a name="ca2aex"></a>  CA2AEX::CA2AEX  
 Der Konstruktor.  
  
```
CA2AEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2AEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *psz*  
 Die Textzeichenfolge, die konvertiert werden.  
  
 *nCodePage*  
 Wenn Sie nicht in dieser Klasse verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt den Puffer für die Übersetzung erforderlich sind.  
  
##  <a name="dtor"></a>  CA2AEX:: ~ CA2AEX  
 Der Destruktor.  
  
```
~CA2AEX() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt den zugeordneten Puffer frei.  
  
##  <a name="m_psz"></a>  CA2AEX::m_psz  
 Der Datenmember, die die Quellzeichenfolge speichert.  
  
```
LPSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>  CA2AEX::m_szBuffer  
 Die statischen Puffer, der zum Speichern der konvertierten Zeichenfolge.  
  
```
char m_szBuffer[ t_nBufferLength];
```  
  
##  <a name="operator_lpstr"></a>  CA2AEX::Operator LPSTR  
 Konvertierungsoperator.  
  
```
operator LPSTR() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Zeichenfolge zurück, LPSTR eingeben.  
  
## <a name="see-also"></a>Siehe auch  
 [CA2CAEX-Klasse](../../atl/reference/ca2caex-class.md)   
 [CA2WEX-Klasse](../../atl/reference/ca2wex-class.md)   
 [CW2AEX-Klasse](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX-Klasse](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX-Klasse](../../atl/reference/cw2wex-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)