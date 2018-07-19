---
title: CA2WEX-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CA2WEX
- ATLCONV/ATL::CA2WEX
- ATLCONV/ATL::CA2WEX::CA2WEX
- ATLCONV/ATL::CA2WEX::m_psz
- ATLCONV/ATL::CA2WEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CA2WEX class
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f19046cc825fabd2a3a41020a9f4c141dc98489e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882818"
---
# <a name="ca2wex-class"></a>CA2WEX-Klasse
Diese Klasse wird von der Zeichenfolgen-konvertierungsmakros CA2TEX, CA2CTEX, CT2WEX, CT2CWEX wird und der Typedef CA2W verwendet.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <int t_nBufferLength = 128>
class CA2WEX
```  
  
#### <a name="parameters"></a>Parameter  
 *t_nBufferLength*  
 Die Größe des Puffers, die in der Übersetzungsprozess verwendet werden soll. Die Standardeinstellung ist 128 Bytes.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2WEX::CA2WEX](#ca2wex)|Der Konstruktor.|  
|[CA2WEX:: ~ CA2WEX](#dtor)|Der Destruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2WEX::Operator LPWSTR](#operator_lpwstr)|Konvertierungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2WEX::m_psz](#m_psz)|Der Datenmember, die die Quellzeichenfolge speichert.|  
|[CA2WEX::m_szBuffer](#m_szbuffer)|Die statischen Puffer, der zum Speichern der konvertierten Zeichenfolge.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn zusätzliche Funktionalität erforderlich ist, verwenden Sie CA2TEX CA2CTEX, CT2WEX, CT2CWEX oder CA2W in Ihrem Code.  
  
 Diese Klasse enthält einen statischen Puffer mit fester Größe, mit der das Ergebnis der Konvertierung zu speichern. Wenn das Ergebnis zu groß, um in den statischen Puffer zu passen, weist die Klasse Speicher verwenden **Malloc**, den Speicher freigibt, wenn das Objekt den Gültigkeitsbereich verlässt. Dadurch wird sichergestellt, dass im Gegensatz zu Text konvertierungsmakros, die in früheren Versionen von ATL, dieser Klasse sicher in Schleifen verwendet werden kann und es der Stack overflow wird nicht verfügbar.  
  
 Wenn die Klasse versucht, die speicherbelegung auf dem Heap und ein Fehler auftritt, ruft sie `AtlThrow` mit einem Argument von E_OUTOFMEMORY.  
  
 Standardmäßig verwenden die ATL-konvertierungsklassen und-Makros ANSI-Codepage des aktuellen Threads für die Konvertierung. Wenn Sie dieses Verhalten für eine bestimmte Konvertierung überschreiben möchten, geben Sie die Codepage, als zweiten Parameter an den Konstruktor für die Klasse.  
  
 Die folgenden Makros basieren auf diese Klasse:  
  
- CA2TEX  
  
- CA2CTEX  
  
- CT2WEX  
  
- CT2CWEX  
  
 Die folgende Typedef basiert auf diese Klasse:  
  
- CA2W  
  
 Eine Erläuterung der diese textkonvertierungsmakros, finden Sie unter [ATL- und MFC-Zeichenfolgen-Konvertierungsmakros](string-conversion-macros.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [ATL- und MFC-Zeichenfolgen-Konvertierungsmakros](string-conversion-macros.md) für ein Beispiel für diese Zeichenfolgen-konvertierungsmakros.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlconv.h  
  
##  <a name="ca2wex"></a>  CA2WEX::CA2WEX  
 Der Konstruktor.  
  
```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *psz*  
 Die Textzeichenfolge, die konvertiert werden.  
  
 *nCodePage*  
 Die Codepage, die zum Durchführen der Konvertierung verwendet wird. Lesen Sie die Code-Seite Parameter Beiträge für die Windows SDK-Funktion [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072) Weitere Details.  
  
### <a name="remarks"></a>Hinweise  
 Weist den Puffer, in der Übersetzungsprozess verwendet.  
  
##  <a name="dtor"></a>  CA2WEX:: ~ CA2WEX  
 Der Destruktor.  
  
```
~CA2WEX() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt den zugeordneten Puffer frei.  
  
##  <a name="m_psz"></a>  CA2WEX::m_psz  
 Der Datenmember, die die Quellzeichenfolge speichert.  
  
```
LPWSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>  CA2WEX::m_szBuffer  
 Die statischen Puffer, der zum Speichern der konvertierten Zeichenfolge.  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpwstr"></a>  CA2WEX::Operator LPWSTR  
 Konvertierungsoperator.  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Zeichenfolge, LPWSTR eingeben.  
  
## <a name="see-also"></a>Siehe auch  
 [CA2AEX-Klasse](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX-Klasse](../../atl/reference/ca2caex-class.md)   
 [CW2AEX-Klasse](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX-Klasse](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX-Klasse](../../atl/reference/cw2wex-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
