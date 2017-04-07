---
title: CStrBufT Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStrBufT
- ATLSIMPSTR/ATL::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::SetLength
- ATLSIMPSTR/ATL::CStrBufT::AUTO_LENGTH
- ATLSIMPSTR/ATL::CStrBufT::SET_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
caps.latest.revision: 17
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
ms.openlocfilehash: 2eb551d2db029de88aa9c1b456c44609b7fc0922
ms.lasthandoff: 02/24/2017

---
# <a name="cstrbuft-class"></a>CStrBufT-Klasse
Diese Klasse ermöglicht die automatische Bereinigung für `GetBuffer` und `ReleaseBuffer` aufruft, die auf einer vorhandenen `CStringT` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename TCharType>
class CStrBufT
```  
  
#### <a name="parameters"></a>Parameter  
 *TCharType*  
 Den Zeichentyp, der die `CStrBufT` Klasse. Einer der folgenden Werte ist möglich:  
  
- `char`(für ANSI-Zeichenfolgen)  
  
- `wchar_t`(für Unicode-Zeichenfolgen)  
  
- **TCHAR** (nach ANSI- und Unicode-Zeichenfolgen)  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`PCXSTR`|Ein Zeiger auf eine Konstante Zeichenfolge.|  
|`PXSTR`|Ein Zeiger auf eine Zeichenfolge.|  
|`StringType`|Die Zeichenfolgentyp, dessen Puffer von spezialisierungen dieser Klasse Vorlage bearbeitet werden.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStrBufT::CStrBufT](#cstrbuft)|Der Konstruktor für den Puffer Zeichenfolgenobjekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStrBufT::SetLength](#setlength)|Legt die Länge des zugeordneten Objekts Zeichen fest.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStrBufT::operator PCXSTR](#operator_pcxstr)|Ruft eine **const** Zeiger auf den Zeichenpuffer zugeordnete String-Objekt.|  
|[CStrBufT::operator PXSTR](#operator_pxstr)|Ruft einen Zeiger auf den Zeichenpuffer des zugeordneten Objekts ab.|  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStrBufT::AUTO_LENGTH](#auto_length)|Bestimmt automatisch die neue Länge der Zeichenfolge in der Version.|  
|[CStrBufT::SET_LENGTH](#set_length)|Festlegen Sie die Länge des Zeichenfolgenobjekts beim GetBuffer|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse dient als Wrapperklasse für den Austausch Aufrufe [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) und [ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer), oder [GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) und `ReleaseBuffer`.  
  
 In erster Linie als eine Hilfsklasse entwickelt `CStrBufT` bietet eine bequeme Möglichkeit für einen Entwickler mit den Zeichenpuffer eines Zeichenfolgenobjekts arbeiten, ohne sich Gedanken darüber, wie zu oder Aufruf `ReleaseBuffer`. Dies ist möglich, da das Wrapperobjekt Bereich natürlich im Fall einer Ausnahme oder mehrere vorhandene Codepfade verlässt; der Destruktor die Zeichenfolgenressource freizugeben, verursacht.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpstr.h  
  
##  <a name="auto_length"></a>CStrBufT::AUTO_LENGTH  
 Bestimmt automatisch die neue Länge der Zeichenfolge in der Version.  
  
```
static const DWORD AUTO_LENGTH = 0x01;
```  
  
### <a name="remarks"></a>Hinweise  
 Bestimmt automatisch die neue Länge der Zeichenfolge in der Version. Die Zeichenfolge muss Null-terminiert sein.  
  
##  <a name="cstrbuft"></a>CStrBufT::CStrBufT  
 Erstellt einen Pufferobjekt.  
  
```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `str`  
 Das String-Objekt, das den Puffer zugeordnet ist. In der Regel verwendet der Entwickler der voreingestellten Typdefinitionen **CStrBuf** ( **TCHAR** Variante), **CStrBufA** ( `char` Variant-Wert) und **CStrBufW** ( `wchar_t` Variante).  
  
 *nMinLength*  
 Die minimale Länge des Zeichenpuffers.  
  
 `dwFlags`  
 Bestimmt, ob die Länge der Zeichenfolge automatisch bestimmt wird. Einer der folgenden Werte ist möglich:  
  
- **AUTO_LENGTH** Zeichenfolgenlänge wird automatisch bestimmt, wann [CSimpleStringT::Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) aufgerufen wird. Die Zeichenfolge muss Null-terminiert sein. Der Standardwert.  
  
- **SET_LENGTH** Länge der Zeichenfolge festgelegt wird, wenn [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) aufgerufen wird.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt einen Zeichenfolgenpuffer für das Objekt zugeordnete Zeichenfolge. Während der Konstruktion [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) oder [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) aufgerufen wird.  
  
 Beachten Sie, dass der Kopierkonstruktor `private`.  
  
##  <a name="operator_pcxstr"></a>CStrBufT::operator PCXSTR  
 Direkt greift auf Zeichen in dem Objekt zugeordnete Zeichenfolge als Zeichenfolge im C-Format gespeichert.  
  
```  
operator PCXSTR() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeichenzeiger von der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um einen Zeiger auf den Zeichenpuffer ein String-Objekt zurückzugeben. Mit diesem Zeiger können den Inhalt der String-Objekt geändert werden.  
  
##  <a name="operator_pxstr"></a>CStrBufT::operator PXSTR  
 Direkt greift auf Zeichen in dem Objekt zugeordnete Zeichenfolge als Zeichenfolge im C-Format gespeichert.  
  
```
operator PXSTR() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeichenzeiger von der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um einen Zeiger auf den Zeichenpuffer ein String-Objekt zurückzugeben. Der Entwickler kann den Inhalt der String-Objekt mit dieser Zeiger ändern.  
  
##  <a name="pcxstr"></a>CStrBufT::PCXSTR  
 Ein Zeiger auf eine Konstante Zeichenfolge.  
  
```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```  
  
##  <a name="pxstr"></a>CStrBufT::PXSTR  
 Ein Zeiger auf eine Zeichenfolge.  
  
```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```  
  
##  <a name="set_length"></a>CStrBufT::SET_LENGTH  
 Legen Sie das String-Objekt am `GetBuffer` Zeit.  
  
```
static const DWORD SET_LENGTH = 0x02;
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie die Länge des Zeichenfolgenobjekts GetBuffer Zeitpunkt fest.  
  
 Bestimmt, ob [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) und [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) werden aufgerufen, wenn die Zeichenfolge TextBuffer-Objekt erstellt wird.  
  
##  <a name="setlength"></a>CStrBufT::SetLength  
 Legt die Länge des Zeichenpuffers fest.  
  
```
void SetLength(int nLength);
```  
  
### <a name="parameters"></a>Parameter  
 `nLength`  
 Die neue Länge des Puffers Zeichen des String-Objekt.  
  
> [!NOTE]
>  Muss kleiner oder gleich der im Konstruktor angegebenen Mindestgröße des Puffers Länge `CStrBufT`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um die Länge der Zeichenfolge, die vom Pufferobjekt dargestellt.  
  
##  <a name="stringtype"></a>CStrBufT::StringType  
 Die Zeichenfolgentyp, dessen Puffer von spezialisierungen dieser Klasse Vorlage bearbeitet werden.  
  
```
typedef CSimpleStringT<TCharType> StringType;
```  
  
### <a name="remarks"></a>Hinweise  
 **TCharType** ist der Zeichentyp verwendet, um die Klassenvorlage.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL/MFC-freigegeben Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)



