---
title: Klasse CA2AEX | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 65637b63cf23d2e7433b575e95d3f53a53ed76a1
ms.lasthandoff: 02/24/2017

---
# <a name="ca2aex-class"></a>CA2AEX-Klasse
Diese Klasse wird verwendet, indem die zeichenfolgenkonvertierungsmakros `CA2TEX` und `CT2AEX`, und die Typedef **CA2A**.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <int t_nBufferLength = 128>
class CA2AEX
```  
  
#### <a name="parameters"></a>Parameter  
 `t_nBufferLength`  
 Die Größe des Puffers im Übersetzungsprozess. Die Standardlänge beträgt 128 Byte.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2AEX::CA2AEX](#ca2aex)|Der Konstruktor.|  
|[CA2AEX:: ~ CA2AEX](#dtor)|Der Destruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2AEX::Operator LPSTR](#operator_lpstr)|Operator für die Konvertierung.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2AEX::m_psz](#m_psz)|Der Datenmember, die die Quellzeichenfolge speichert.|  
|[CA2AEX::m_szBuffer](#m_szbuffer)|Den statischen Puffer zum Speichern der konvertierten Zeichenfolge verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn zusätzlicher Funktionalität erforderlich ist, verwenden Sie `CA2TEX`, `CT2AEX`, oder **CA2A** in Ihrem eigenen Code.  
  
 Diese Klasse enthält einen statische Puffer mit fester Größe die verwendet wird, um das Ergebnis der Konvertierung zu speichern. Wenn das Ergebnis zu groß ist, um in den statischen Puffer zu passen, weist die Klasse mittels `malloc` Arbeitsspeicher zu und gibt den Speicher wieder frei, wenn das Objekt sich nicht mehr im Gültigkeitsbereich befindet. Dadurch wird sichergestellt, dass im Gegensatz zu Text konvertierungsmakros, die in früheren Versionen von ATL, diese Klasse sicher in Schleifen verwendet werden kann und dass es die Stapelüberlauf wird nicht verfügbar.  
  
 Wenn die Klasse versucht, Speicher auf dem Heap und ein Fehler auftritt, ruft er `AtlThrow` mit dem Argument **E_OUTOFMEMORY**.  
  
 Standardmäßig verwenden die ATL-konvertierungsklassen und-Makros ANSI-Codepage des aktuellen Threads für die Konvertierung.  
  
 Die folgenden Makros basieren auf diese Klasse:  
  
- `CA2TEX`  
  
- `CT2AEX`  
  
 Die folgende Typedef basiert auf diese Klasse:  
  
- **CA2A**  
  
 Eine Beschreibung dieser textkonvertierungsmakros, finden Sie unter [ATL und MFC-Makros zur Zeichenfolgenkonvertierung](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [ATL und MFC-Makros zur Zeichenfolgenkonvertierung](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863) ein Beispiel für die Verwendung dieser Makros für die Konvertierung.  
  
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
 Die Textzeichenfolge konvertiert werden.  
  
 `nCodePage`  
 In dieser Klasse wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt für die Übersetzung erforderliche Puffers.  
  
##  <a name="dtor"></a>CA2AEX:: ~ CA2AEX  
 Der Destruktor.  
  
```
~CA2AEX() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt den zugeordneten Puffer frei.  
  
##  <a name="m_psz"></a>CA2AEX::m_psz  
 Der Datenmember, die die Quellzeichenfolge speichert.  
  
```
LPSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>CA2AEX::m_szBuffer  
 Den statischen Puffer zum Speichern der konvertierten Zeichenfolge verwendet.  
  
```
char m_szBuffer[ t_nBufferLength];
```  
  
##  <a name="operator_lpstr"></a>CA2AEX::Operator LPSTR  
 Operator für die Konvertierung.  
  
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
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
