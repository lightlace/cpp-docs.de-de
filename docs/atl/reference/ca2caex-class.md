---
title: CA2CAEX Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CA2CAEX
- ATLCONV/ATL::CA2CAEX
- ATLCONV/ATL::CA2CAEX::CA2CAEX
- ATLCONV/ATL::CA2CAEX::m_psz
dev_langs: C++
helpviewer_keywords: CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0ae0db059d092feb1a24a3c7c635817250f2813b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ca2caex-class"></a>CA2CAEX-Klasse
Diese Klasse wird verwendet, von Makros zur zeichenfolgenkonvertierung `CA2CTEX` und `CT2CAEX`, und die Typedef **CA2CA**.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<int t_nBufferLength = 128>  
class CA2CAEX
```  
  
#### <a name="parameters"></a>Parameter  
 `t_nBufferLength`  
 Die Größe des Puffers, der bei der Übersetzung verwendet werden soll. Die Standardlänge beträgt 128 Bytes.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2CAEX::CA2CAEX](#ca2caex)|Der Konstruktor.|  
|[CA2CAEX:: ~ CA2CAEX](#dtor)|Der Destruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2CAEX::Operator LPCSTR](#operator_lpcstr)|Konvertierungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CA2CAEX::m_psz](#m_psz)|Das Datenelement, das die Quellzeichenfolge speichert.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn zusätzlicher Funktionalität erforderlich ist, verwenden Sie `CA2CTEX`, `CT2CAEX`, oder **CA2CA** in Ihrem eigenen Code.  
  
 Diese Klasse ist sicher in Schleifen verwendet und wird nicht zu einem Stapelüberlauf. Standardmäßig verwenden die ATL-Konvertierungsklassen und -makros für die Konvertierung die ANSI-Codeseite des aktuellen Threads.  
  
 Die folgenden Makros hängen von dieser Klasse:  
  
- `CA2CTEX`  
  
- `CT2CAEX`  
  
 Die folgenden Typedef basiert auf diese Klasse:  
  
- **CA2CA**  
  
 Eine Erläuterung der diese textkonvertierungsmakros, finden Sie unter [ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](string-conversion-macros.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](string-conversion-macros.md) für ein Beispiel zur Verwendung dieser Makros zur zeichenfolgenkonvertierung.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlconv.h  
  
##  <a name="ca2caex"></a>CA2CAEX::CA2CAEX  
 Der Konstruktor.  
  
```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die Textzeichenfolge, die konvertiert werden.  
  
 `nCodePage`  
 In dieser Klasse wird nicht verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt den Puffer für die Übersetzung erforderlich.  
  
##  <a name="dtor"></a>CA2CAEX:: ~ CA2CAEX  
 Der Destruktor.  
  
```
~CA2CAEX() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt den zugeordneten Puffer frei.  
  
##  <a name="m_psz"></a>CA2CAEX::m_psz  
 Das Datenelement, das die Quellzeichenfolge speichert.  
  
```
LPCSTR m_psz;
```  
  
##  <a name="operator_lpcstr"></a>CA2CAEX::Operator LPCSTR  
 Konvertierungsoperator.  
  
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
 [Klassenübersicht](../../atl/atl-class-overview.md)
