---
title: CStrBufT Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 695c3bc4c5e03f2ff6c1865f456b1ef358e3dcf4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361357"
---
# <a name="cstrbuft-class"></a>CStrBufT-Klasse
Diese Klasse bietet automatische ressourcenbereinigung für `GetBuffer` und `ReleaseBuffer` aufruft, die auf einer vorhandenen `CStringT` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename TCharType>
class CStrBufT
```  
  
#### <a name="parameters"></a>Parameter  
 *TCharType*  
 Der Zeichentyp, der die `CStrBufT` Klasse. Einer der folgenden Werte ist möglich:  
  
- `char` (für ANSI-Zeichenfolgen)  
  
- `wchar_t` (für Unicode-Zeichenfolgen)  
  
- **TCHAR** (für ANSI- und Unicode-Zeichenfolgen)  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`PCXSTR`|Ein Zeiger auf eine Konstante Zeichenfolge.|  
|`PXSTR`|Ein Zeiger auf eine Zeichenfolge.|  
|`StringType`|Die Zeichenfolgentyp, dessen Puffer vom spezialisierungen dieser Klassenvorlage bearbeitet werden.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStrBufT::CStrBufT](#cstrbuft)|Der Konstruktor für den Puffer String-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStrBufT::SetLength](#setlength)|Legt die Pufferlänge Zeichen des zugeordneten Objekts fest.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStrBufT::operator PCXSTR](#operator_pcxstr)|Ruft eine **const** Zeiger auf der Zeichenpuffer zugeordnete String-Objekt.|  
|[CStrBufT::operator PXSTR](#operator_pxstr)|Ruft einen Zeiger auf der Zeichenpuffer des zugeordneten Objekts ab.|  
  
### <a name="public-constants"></a>Öffentliche Konstanten  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CStrBufT::AUTO_LENGTH](#auto_length)|Bestimmt automatisch die neue Länge der Zeichenfolge in der Version aus.|  
|[CStrBufT::SET_LENGTH](#set_length)|Legen Sie die Länge eines Zeichenfolgenobjekts GetBuffer Zeitpunkt|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse dient als eine Wrapperklasse für Aufrufe von ersetzen [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) und [ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer), oder [GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) und `ReleaseBuffer`.  
  
 In erster Linie als eine Hilfsklasse entworfen `CStrBufT` bietet eine einfache Möglichkeit für Entwickler arbeiten mit der Zeichenpuffer eines Zeichenfolgenobjekts ohne Rücksicht auf wie oder beim Aufrufen `ReleaseBuffer`. Dies ist möglich, da der Wrapper-Objekt den Gültigkeitsbereich natürlich im Falle eines Fehlers oder mehrere vorhandene Codepfade verlässt; verursacht sein Destruktor Zeichenfolgenressource freizugeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpstr.h  
  
##  <a name="auto_length"></a>  CStrBufT::AUTO_LENGTH  
 Bestimmt automatisch die neue Länge der Zeichenfolge in der Version aus.  
  
```
static const DWORD AUTO_LENGTH = 0x01;
```  
  
### <a name="remarks"></a>Hinweise  
 Bestimmt automatisch die neue Länge der Zeichenfolge in der Version aus. Die Zeichenfolge muss Null-terminiert sein.  
  
##  <a name="cstrbuft"></a>  CStrBufT::CStrBufT  
 Erstellt einen Pufferobjekt.  
  
```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `str`  
 Das String-Objekt, das den Puffer zugeordnet ist. In der Regel verwendet der Entwickler der voreingestellten Typdefinitionen **CStrBuf** ( **TCHAR** Variante), **CStrBufA** ( `char` Variante) und **CStrBufW**  ( `wchar_t` Variant-Wert).  
  
 *nMinLength*  
 Die Mindestlänge von der Zeichenpuffer.  
  
 `dwFlags`  
 Bestimmt, ob die Länge der Zeichenfolge automatisch bestimmt wird. Einer der folgenden Werte ist möglich:  
  
- **AUTO_LENGTH** Zeichenfolgenlänge wird automatisch bestimmt, wann [CSimpleStringT::Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) aufgerufen wird. Die Zeichenfolge muss Null-terminiert sein. Der Standardwert.  
  
- **SET_LENGTH** Zeichenfolgenlänge wird festgelegt, wenn [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) aufgerufen wird.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt einen Zeichenfolgenpuffer für das zugeordnete String-Objekt. Während der Erstellung [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) oder [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) aufgerufen wird.  
  
 Beachten Sie, dass der Kopierkonstruktor `private`.  
  
##  <a name="operator_pcxstr"></a>  CStrBufT::operator PCXSTR  
 Greift auf direkt zu Zeichen, die im zugeordneten String-Objekt als Zeichenfolge im C-Format gespeichert.  
  
```  
operator PCXSTR() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeichenzeiger auf den String-Daten.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um einen Zeiger auf ein Zeichenfolgenobjekt, das der Zeichenpuffer zurückzugeben. Mit dieser Zeiger können den Inhalt von der String-Objekt geändert werden.  
  
##  <a name="operator_pxstr"></a>  CStrBufT::operator PXSTR  
 Greift auf direkt zu Zeichen, die im zugeordneten String-Objekt als Zeichenfolge im C-Format gespeichert.  
  
```
operator PXSTR() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeichenzeiger auf den String-Daten.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um einen Zeiger auf ein Zeichenfolgenobjekt, das der Zeichenpuffer zurückzugeben. Der Entwickler kann den Inhalt von der String-Objekt mit dieser Zeiger ändern.  
  
##  <a name="pcxstr"></a>  CStrBufT::PCXSTR  
 Ein Zeiger auf eine Konstante Zeichenfolge.  
  
```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```  
  
##  <a name="pxstr"></a>  CStrBufT::PXSTR  
 Ein Zeiger auf eine Zeichenfolge.  
  
```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```  
  
##  <a name="set_length"></a>  CStrBufT::SET_LENGTH  
 Legen Sie die von der String-Objekt am `GetBuffer` Zeit.  
  
```
static const DWORD SET_LENGTH = 0x02;
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie GetBuffer zum Zeitpunkt der String-Objekt fest.  
  
 Bestimmt, ob [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) und [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) werden aufgerufen, wenn der Puffer String-Objekt erstellt wird.  
  
##  <a name="setlength"></a>  CStrBufT::SetLength  
 Legt die Länge der Zeichenpuffer fest.  
  
```
void SetLength(int nLength);
```  
  
### <a name="parameters"></a>Parameter  
 `nLength`  
 Die neue Länge des der Zeichenpuffer String-Objekt.  
  
> [!NOTE]
>  Muss kleiner oder gleich der im Konstruktor der angegebenen Mindestgröße des Pufferlänge `CStrBufT`.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Festlegen der Länge der Zeichenfolge, die vom Pufferobjekt dargestellt wird.  
  
##  <a name="stringtype"></a>  CStrBufT::StringType  
 Die Zeichenfolgentyp, dessen Puffer vom spezialisierungen dieser Klassenvorlage bearbeitet werden.  
  
```
typedef CSimpleStringT<TCharType> StringType;
```  
  
### <a name="remarks"></a>Hinweise  
 **TCharType** ist der Zeichentyp verwendet, um die Klassenvorlage.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)


