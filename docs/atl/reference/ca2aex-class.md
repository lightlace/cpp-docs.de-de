---
title: CA2AEX Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CA2AEX
- ATLCONV/ATL::CA2AEX
- ATLCONV/ATL::CA2AEX::CA2AEX
- ATLCONV/ATL::CA2AEX::m_psz
- ATLCONV/ATL::CA2AEX::m_szBuffer
dev_langs: C++
helpviewer_keywords: CA2AEX class
ms.assetid: 57dc65df-d9cf-4a84-99d3-6e031dde3664
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d682e6db093220557ec7caaa4ac6f3cd7ca5f53a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ca2aex-class"></a>CA2AEX-Klasse
Diese Klasse wird verwendet, indem die Makros zur zeichenfolgenkonvertierung `CA2TEX` und `CT2AEX`, und die Typedef **CA2A**.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <int t_nBufferLength = 128>
class CA2AEX
```  
  
#### <a name="parameters"></a>Parameter  
 `t_nBufferLength`  
 Die Größe des Puffers, der bei der Übersetzung verwendet werden soll. Die Standardlänge beträgt 128 Bytes.  
  
## <a name="members"></a>Mitglieder  
  
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
|[CA2AEX::m_psz](#m_psz)|Das Datenelement, das die Quellzeichenfolge speichert.|  
|[CA2AEX::m_szBuffer](#m_szbuffer)|Den statischen Puffer zum Speichern der konvertierten Zeichenfolge verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn zusätzlicher Funktionalität erforderlich ist, verwenden Sie `CA2TEX`, `CT2AEX`, oder **CA2A** in Ihrem eigenen Code.  
  
 Diese Klasse enthält einen statischen Puffer mit fester Größe, mit der das Ergebnis der Konvertierung zu speichern. Wenn das Ergebnis zu groß ist, um in den statischen Puffer zu passen, weist die Klasse mittels `malloc` Arbeitsspeicher zu und gibt den Speicher wieder frei, wenn das Objekt sich nicht mehr im Gültigkeitsbereich befindet. Dadurch wird sichergestellt, dass im Gegensatz zu Text konvertierungsmakros, die in früheren Versionen von ATL, diese Klasse sicher in Schleifen verwendet werden kann, sodass er den Stapel "Überlauf" wird nicht verfügbar.  
  
 Wenn die Klasse versucht, Zuweisen von Arbeitsspeicher auf dem Heap und ein Fehler auftritt, er ruft `AtlThrow` mit dem Argument **E_OUTOFMEMORY**.  
  
 Standardmäßig verwenden die ATL-konvertierungsklassen und-Makros ANSI-Codepage für den aktuellen Thread für die Konvertierung.  
  
 Die folgenden Makros hängen von dieser Klasse:  
  
- `CA2TEX`  
  
- `CT2AEX`  
  
 Die folgenden Typedef basiert auf diese Klasse:  
  
- **CA2A**  
  
 Eine Erläuterung der diese textkonvertierungsmakros, finden Sie unter [ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](string-conversion-macros.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](string-conversion-macros.md) für ein Beispiel zur Verwendung dieser Makros zur zeichenfolgenkonvertierung.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlconv.h  
  
##  <a name="ca2aex"></a>CA2AEX::CA2AEX  
 Der Konstruktor.  
  
```
CA2AEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2AEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die Textzeichenfolge, die konvertiert werden.  
  
 `nCodePage`  
 In dieser Klasse wird nicht verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt den Puffer für die Übersetzung erforderlich.  
  
##  <a name="dtor"></a>CA2AEX:: ~ CA2AEX  
 Der Destruktor.  
  
```
~CA2AEX() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt den zugeordneten Puffer frei.  
  
##  <a name="m_psz"></a>CA2AEX::m_psz  
 Das Datenelement, das die Quellzeichenfolge speichert.  
  
```
LPSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>CA2AEX::m_szBuffer  
 Den statischen Puffer zum Speichern der konvertierten Zeichenfolge verwendet.  
  
```
char m_szBuffer[ t_nBufferLength];
```  
  
##  <a name="operator_lpstr"></a>CA2AEX::Operator LPSTR  
 Konvertierungsoperator.  
  
```
operator LPSTR() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Zeichenfolge als Typ **LPSTR**.  
  
## <a name="see-also"></a>Siehe auch  
 [CA2CAEX-Klasse](../../atl/reference/ca2caex-class.md)   
 [CA2WEX-Klasse](../../atl/reference/ca2wex-class.md)   
 [CW2AEX-Klasse](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX-Klasse](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX-Klasse](../../atl/reference/cw2wex-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)