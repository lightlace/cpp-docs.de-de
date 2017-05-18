---
title: CW2AEX Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
caps.latest.revision: 21
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 007dc4a40f0784984981c9b2741ec79ce6f12d9b
ms.contentlocale: de-de
ms.lasthandoff: 03/31/2017

---
# <a name="cw2aex-class"></a>CW2AEX-Klasse
Diese Klasse wird verwendet, indem die Makros zur zeichenfolgenkonvertierung `CT2AEX`, `CW2TEX`, `CW2CTEX`, und `CT2CAEX`, und die Typedef **CW2A**.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<int t_nBufferLength = 128>  
class CW2AEX
```  
  
#### <a name="parameters"></a>Parameter  
 `t_nBufferLength`  
 Die Größe des Puffers, der bei der Übersetzung verwendet werden soll. Die Standardlänge beträgt 128 Bytes.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CW2AEX::CW2AEX](#cw2aex)|Der Konstruktor.|  
|[CW2AEX:: ~ CW2AEX](#dtor)|Der Destruktor.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CW2AEX::Operator LPSTR](#operator_lpstr)|Konvertierungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CW2AEX::m_psz](#m_psz)|Das Datenelement, das die Quellzeichenfolge speichert.|  
|[CW2AEX::m_szBuffer](#m_szbuffer)|Den statischen Puffer zum Speichern der konvertierten Zeichenfolge verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn zusätzlicher Funktionalität erforderlich ist, verwenden Sie `CT2AEX`, `CW2TEX`, `CW2CTEX`, `CT2CAEX`, oder **CW2A** im Code.  
  
 Diese Klasse enthält einen statischen Puffer mit fester Größe, mit der das Ergebnis der Konvertierung zu speichern. Wenn das Ergebnis zu groß ist, um in den statischen Puffer zu passen, weist die Klasse mittels `malloc` Arbeitsspeicher zu und gibt den Speicher wieder frei, wenn das Objekt sich nicht mehr im Gültigkeitsbereich befindet. Dadurch wird sichergestellt, dass im Gegensatz zu Text konvertierungsmakros, die in früheren Versionen von ATL, diese Klasse sicher in Schleifen verwendet werden kann, sodass er den Stapel "Überlauf" wird nicht verfügbar.  
  
 Wenn die Klasse versucht, Zuweisen von Arbeitsspeicher auf dem Heap und ein Fehler auftritt, er ruft `AtlThrow` mit dem Argument **E_OUTOFMEMORY**.  
  
 Standardmäßig verwenden die ATL-konvertierungsklassen und-Makros ANSI-Codepage für den aktuellen Thread für die Konvertierung. Wenn Sie dieses Verhalten für eine spezifische Konvertierung überschreiben möchten, geben Sie die Codepage als zweiten Parameter an den Konstruktor für die Klasse.  
  
 Die folgenden Makros hängen von dieser Klasse:  
  
- `CT2AEX`  
  
- `CW2TEX`  
  
- `CW2CTEX`  
  
- `CT2CAEX`  
  
 Die folgenden Typedef basiert auf diese Klasse:  
  
- **CW2A**  
  
 Eine Erläuterung der diese textkonvertierungsmakros, finden Sie unter [ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](string-conversion-macros.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](string-conversion-macros.md) für ein Beispiel zur Verwendung dieser Makros zur zeichenfolgenkonvertierung.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlconv.h  
  
##  <a name="cw2aex"></a>CW2AEX::CW2AEX  
 Der Konstruktor.  
  
```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2AEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `psz`  
 Die Textzeichenfolge, die konvertiert werden.  
  
 `nCodePage`  
 Die Codepage, die zum Durchführen der Konvertierung verwendet wird. Finden Sie in den Ausführungen Code Seite Parameter, für die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Funktion [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072) Weitere Details.  
  
### <a name="remarks"></a>Hinweise  
 Ordnet den Puffer, der bei der Übersetzung verwendet.  
  
##  <a name="dtor"></a>CW2AEX:: ~ CW2AEX  
 Der Destruktor.  
  
```
~CW2AEX() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt den zugeordneten Puffer frei.  
  
##  <a name="m_psz"></a>CW2AEX::m_psz  
 Das Datenelement, das die Quellzeichenfolge speichert.  
  
```
LPSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>CW2AEX::m_szBuffer  
 Den statischen Puffer zum Speichern der konvertierten Zeichenfolge verwendet.  
  
```
char m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpstr"></a>CW2AEX::Operator LPSTR  
 Konvertierungsoperator.  
  
```  
operator LPSTR() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Zeichenfolge als Typ **LPSTR.**  
  
## <a name="see-also"></a>Siehe auch  
 [CA2AEX-Klasse](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX-Klasse](../../atl/reference/ca2caex-class.md)   
 [CA2WEX-Klasse](../../atl/reference/ca2wex-class.md)   
 [CW2CWEX-Klasse](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX-Klasse](../../atl/reference/cw2wex-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)

