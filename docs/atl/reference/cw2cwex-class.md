---
title: CW2CWEX Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
dev_langs:
- C++
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 671311b0788438d7b92dad9d9137e28cbb88df60
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363281"
---
# <a name="cw2cwex-class"></a>CW2CWEX-Klasse
Diese Klasse wird verwendet, indem die Makros zur zeichenfolgenkonvertierung `CW2CTEX` und `CT2CWEX`, und die Typedef `CW2W`.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<int t_nBufferLength = 128>  
class CW2CWEX
```  
  
#### <a name="parameters"></a>Parameter  
 `t_nBufferLength`  
 Die Größe des Puffers, der bei der Übersetzung verwendet werden soll. Die Standardlänge beträgt 128 Bytes.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CW2CWEX::CW2CWEX](#cw2cwex)|Der Konstruktor.|  
|[CW2CWEX:: ~ CW2CWEX](#dtor)|Der Destruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CW2CWEX::Operator LPCWSTR](#operator_lpcwstr)|Konvertierungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CW2CWEX::m_psz](#m_psz)|Das Datenelement, das die Quellzeichenfolge speichert.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn zusätzlicher Funktionalität erforderlich ist, verwenden Sie `CW2CTEX`, `CT2CWEX`, oder `CW2W` im Code.  
  
 Diese Klasse ist sicher in Schleifen verwendet und wird nicht zu einem Stapelüberlauf. Standardmäßig verwenden die ATL-konvertierungsklassen und-Makros ANSI-Codepage für den aktuellen Thread für die Konvertierung.  
  
 Die folgenden Makros hängen von dieser Klasse:  
  
- `CW2CTEX`  
  
- `CT2CWEX`  
  
 Die folgenden Typedef basiert auf diese Klasse:  
  
- `CW2W`  
  
 Eine Erläuterung der diese textkonvertierungsmakros, finden Sie unter [ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](string-conversion-macros.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](string-conversion-macros.md) für ein Beispiel zur Verwendung dieser Makros zur zeichenfolgenkonvertierung.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlconv.h  
  
##  <a name="cw2cwex"></a>  CW2CWEX::CW2CWEX  
 Der Konstruktor.  
  
```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2CWEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die Textzeichenfolge, die konvertiert werden.  
  
 `nCodePage`  
 Die Codepage. In dieser Klasse verwendet nicht.  
  
### <a name="remarks"></a>Hinweise  
 Ordnet den Puffer, der bei der Übersetzung verwendet.  
  
##  <a name="dtor"></a>  CW2CWEX:: ~ CW2CWEX  
 Der Destruktor.  
  
```
~CW2CWEX() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt den zugeordneten Puffer frei.  
  
##  <a name="m_psz"></a>  CW2CWEX::m_psz  
 Das Datenelement, das die Quellzeichenfolge speichert.  
  
```
LPCWSTR m_psz;
```  
  
##  <a name="operator_lpcwstr"></a>  CW2CWEX::Operator LPCWSTR  
 Konvertierungsoperator.  
  
```  
operator LPCWSTR() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Zeichenfolge als Typ **LPCWSTR.**  
  
## <a name="see-also"></a>Siehe auch  
 [CA2AEX-Klasse](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX-Klasse](../../atl/reference/ca2caex-class.md)   
 [CA2WEX-Klasse](../../atl/reference/ca2wex-class.md)   
 [CW2AEX-Klasse](../../atl/reference/cw2aex-class.md)   
 [CW2WEX-Klasse](../../atl/reference/cw2wex-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
