---
title: CA2WEX Klasse | Microsoft Docs
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
ms.openlocfilehash: 218e0d8f5e93a9e6c41ff855ff086cc7bfa6c766
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358745"
---
# <a name="ca2wex-class"></a>CA2WEX-Klasse
Diese Klasse wird verwendet, indem die Makros zur zeichenfolgenkonvertierung `CA2TEX`, `CA2CTEX`, `CT2WEX`, und `CT2CWEX`, und die Typedef **CA2W**.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <int t_nBufferLength = 128>
class CA2WEX
```  
  
#### <a name="parameters"></a>Parameter  
 `t_nBufferLength`  
 Die Größe des Puffers, der bei der Übersetzung verwendet werden soll. Die Standardlänge beträgt 128 Bytes.  
  
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
|[CA2WEX::m_psz](#m_psz)|Das Datenelement, das die Quellzeichenfolge speichert.|  
|[CA2WEX::m_szBuffer](#m_szbuffer)|Den statischen Puffer zum Speichern der konvertierten Zeichenfolge verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn zusätzlicher Funktionalität erforderlich ist, verwenden Sie `CA2TEX`, `CA2CTEX`, `CT2WEX`, `CT2CWEX`, oder **CA2W** im Code.  
  
 Diese Klasse enthält einen statischen Puffer mit fester Größe, mit der das Ergebnis der Konvertierung zu speichern. Wenn das Ergebnis zu groß ist, um in den statischen Puffer zu passen, weist die Klasse mittels `malloc` Arbeitsspeicher zu und gibt den Speicher wieder frei, wenn das Objekt sich nicht mehr im Gültigkeitsbereich befindet. Dadurch wird sichergestellt, dass im Gegensatz zu Text konvertierungsmakros, die in früheren Versionen von ATL, diese Klasse sicher in Schleifen verwendet werden kann, sodass er den Stapel "Überlauf" wird nicht verfügbar.  
  
 Wenn die Klasse versucht, Zuweisen von Arbeitsspeicher auf dem Heap und ein Fehler auftritt, er ruft `AtlThrow` mit dem Argument **E_OUTOFMEMORY**.  
  
 Standardmäßig verwenden die ATL-konvertierungsklassen und-Makros ANSI-Codepage für den aktuellen Thread für die Konvertierung. Wenn Sie dieses Verhalten für eine spezifische Konvertierung überschreiben möchten, geben Sie die Codepage als zweiten Parameter an den Konstruktor für die Klasse.  
  
 Die folgenden Makros hängen von dieser Klasse:  
  
- `CA2TEX`  
  
- `CA2CTEX`  
  
- `CT2WEX`  
  
- `CT2CWEX`  
  
 Die folgenden Typedef basiert auf diese Klasse:  
  
- **CA2W**  
  
 Eine Erläuterung der diese textkonvertierungsmakros, finden Sie unter [ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](string-conversion-macros.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](string-conversion-macros.md) für ein Beispiel zur Verwendung dieser Makros zur zeichenfolgenkonvertierung.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlconv.h  
  
##  <a name="ca2wex"></a>  CA2WEX::CA2WEX  
 Der Konstruktor.  
  
```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die Textzeichenfolge, die konvertiert werden.  
  
 `nCodePage`  
 Die Codepage, die zum Durchführen der Konvertierung verwendet wird. Finden Sie unter den Ausführungen Code Seite Parameter, für die Windows SDK-Funktion [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072) Weitere Details.  
  
### <a name="remarks"></a>Hinweise  
 Ordnet den Puffer, der bei der Übersetzung verwendet.  
  
##  <a name="dtor"></a>  CA2WEX:: ~ CA2WEX  
 Der Destruktor.  
  
```
~CA2WEX() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt den zugeordneten Puffer frei.  
  
##  <a name="m_psz"></a>  CA2WEX::m_psz  
 Das Datenelement, das die Quellzeichenfolge speichert.  
  
```
LPWSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>  CA2WEX::m_szBuffer  
 Den statischen Puffer zum Speichern der konvertierten Zeichenfolge verwendet.  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpwstr"></a>  CA2WEX::Operator LPWSTR  
 Konvertierungsoperator.  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Zeichenfolge als Typ **LPWSTR.**  
  
## <a name="see-also"></a>Siehe auch  
 [CA2AEX-Klasse](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX-Klasse](../../atl/reference/ca2caex-class.md)   
 [CW2AEX-Klasse](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX-Klasse](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX-Klasse](../../atl/reference/cw2wex-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
