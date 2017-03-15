---
title: Klasse CA2CAEX | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CA2CAEX
- ATL.CA2CAEX<t_nBufferLength>
- ATLCONV/CA2CAEX
- ATL::CA2CAEX<t_nBufferLength>
- ATL::CA2CAEX
- CA2CAEX
dev_langs:
- C++
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
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
ms.openlocfilehash: f104a62144e7fd8ac802c27dfe940a7f96d0e79a
ms.lasthandoff: 02/24/2017

---
# <a name="ca2caex-class"></a>CA2CAEX-Klasse
Diese Klasse wird verwendet, indem zeichenfolgenkonvertierungsmakros `CA2CTEX` und `CT2CAEX`, und die Typedef **CA2CA**.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<int t_nBufferLength = 128>  
class CA2CAEX
```  
  
#### <a name="parameters"></a>Parameter  
 `t_nBufferLength`  
 Die Größe des Puffers im Übersetzungsprozess. Die Standardlänge beträgt 128 Byte.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2CAEX::CA2CAEX](#ca2caex)|Der Konstruktor.|  
|[CA2CAEX:: ~ CA2CAEX](#dtor)|Der Destruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2CAEX::Operator LPCSTR](#operator_lpcstr)|Operator für die Konvertierung.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2CAEX::m_psz](#m_psz)|Der Datenmember, die die Quellzeichenfolge speichert.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn zusätzlicher Funktionalität erforderlich ist, verwenden Sie `CA2CTEX`, `CT2CAEX`, oder **CA2CA** in Ihrem eigenen Code.  
  
 Diese Klasse ist sicher in Schleifen verwendet und wird nicht zu einem Stapelüberlauf. Standardmäßig verwenden die ATL-Konvertierungsklassen und -makros für die Konvertierung die ANSI-Codeseite des aktuellen Threads.  
  
 Die folgenden Makros basieren auf diese Klasse:  
  
- `CA2CTEX`  
  
- `CT2CAEX`  
  
 Die folgende Typedef basiert auf diese Klasse:  
  
- **CA2CA**  
  
 Eine Beschreibung dieser textkonvertierungsmakros, finden Sie unter [ATL und MFC-Makros zur Zeichenfolgenkonvertierung](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [ATL und MFC-Makros zur Zeichenfolgenkonvertierung](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863) ein Beispiel für die Verwendung dieser Makros für die Konvertierung.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlconv.h  
  
##  <a name="a-nameca2caexa--ca2caexca2caex"></a><a name="ca2caex"></a>CA2CAEX::CA2CAEX  
 Der Konstruktor.  
  
```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die Textzeichenfolge konvertiert werden.  
  
 `nCodePage`  
 In dieser Klasse wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt für die Übersetzung erforderliche Puffers.  
  
##  <a name="a-namedtora--ca2caexca2caex"></a><a name="dtor"></a>CA2CAEX:: ~ CA2CAEX  
 Der Destruktor.  
  
```
~CA2CAEX() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt den zugeordneten Puffer frei.  
  
##  <a name="a-namempsza--ca2caexmpsz"></a><a name="m_psz"></a>CA2CAEX::m_psz  
 Der Datenmember, die die Quellzeichenfolge speichert.  
  
```
LPCSTR m_psz;
```  
  
##  <a name="a-nameoperatorlpcstra--ca2caexoperator-lpcstr"></a><a name="operator_lpcstr"></a>CA2CAEX::Operator LPCSTR  
 Operator für die Konvertierung.  
  
```  
operator LPCSTR() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Zeichenfolge als Typ `LPCSTR`.  
  
## <a name="see-also"></a>Siehe auch  
 [CA2AEX-Klasse](../../atl/reference/ca2aex-class.md)   
 [CA2WEX-Klasse](../../atl/reference/ca2wex-class.md)   
 [CW2AEX-Klasse](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX-Klasse](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX-Klasse](../../atl/reference/cw2wex-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

