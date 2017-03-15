---
title: Klasse CW2CWEX | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CW2CWEX
- ATL::CW2CWEX
- ATL.CW2CWEX
- ATL.CW2CWEX<t_nBufferLength>
- ATL::CW2CWEX<t_nBufferLength>
dev_langs:
- C++
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a85b67a58553dada36f4472ea0683e18bc775493
ms.lasthandoff: 02/24/2017

---
# <a name="cw2cwex-class"></a>CW2CWEX-Klasse
Diese Klasse wird verwendet, indem die zeichenfolgenkonvertierungsmakros `CW2CTEX` und `CT2CWEX`, und die Typedef `CW2W`.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<int t_nBufferLength = 128>  
class CW2CWEX
```  
  
#### <a name="parameters"></a>Parameter  
 `t_nBufferLength`  
 Die Größe des Puffers im Übersetzungsprozess. Die Standardlänge beträgt 128 Byte.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CW2CWEX::CW2CWEX](#cw2cwex)|Der Konstruktor.|  
|[CW2CWEX:: ~ CW2CWEX](#dtor)|Der Destruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CW2CWEX::Operator LPCWSTR](#operator_lpcwstr)|Operator für die Konvertierung.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CW2CWEX::m_psz](#m_psz)|Der Datenmember, die die Quellzeichenfolge speichert.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn zusätzlicher Funktionalität erforderlich ist, verwenden Sie `CW2CTEX`, `CT2CWEX`, oder `CW2W` in Ihrem Code.  
  
 Diese Klasse ist sicher in Schleifen verwendet und wird nicht zu einem Stapelüberlauf. Standardmäßig verwenden die ATL-konvertierungsklassen und-Makros ANSI-Codepage des aktuellen Threads für die Konvertierung.  
  
 Die folgenden Makros basieren auf diese Klasse:  
  
- `CW2CTEX`  
  
- `CT2CWEX`  
  
 Die folgende Typedef basiert auf diese Klasse:  
  
- `CW2W`  
  
 Eine Beschreibung dieser textkonvertierungsmakros, finden Sie unter [ATL und MFC-Makros zur Zeichenfolgenkonvertierung](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [ATL und MFC-Makros zur Zeichenfolgenkonvertierung](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863) ein Beispiel für die Verwendung dieser Makros für die Konvertierung.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlconv.h  
  
##  <a name="a-namecw2cwexa--cw2cwexcw2cwex"></a><a name="cw2cwex"></a>CW2CWEX::CW2CWEX  
 Der Konstruktor.  
  
```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2CWEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die Textzeichenfolge konvertiert werden.  
  
 `nCodePage`  
 Die Codepage. In dieser Klasse verwendet nicht.  
  
### <a name="remarks"></a>Hinweise  
 Weist den Puffer im Übersetzungsprozess verwendet.  
  
##  <a name="a-namedtora--cw2cwexcw2cwex"></a><a name="dtor"></a>CW2CWEX:: ~ CW2CWEX  
 Der Destruktor.  
  
```
~CW2CWEX() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt den zugeordneten Puffer frei.  
  
##  <a name="a-namempsza--cw2cwexmpsz"></a><a name="m_psz"></a>CW2CWEX::m_psz  
 Der Datenmember, die die Quellzeichenfolge speichert.  
  
```
LPCWSTR m_psz;
```  
  
##  <a name="a-nameoperatorlpcwstra--cw2cwexoperator-lpcwstr"></a><a name="operator_lpcwstr"></a>CW2CWEX::Operator LPCWSTR  
 Operator für die Konvertierung.  
  
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
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

