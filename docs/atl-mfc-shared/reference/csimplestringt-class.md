---
title: CSimpleStringT Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CSimpleStringT
- ATL::CSimpleStringT
- ATL::CSimpleStringT<BaseType>
- ATL.CSimpleStringT<BaseType>
- CSimpleStringT
dev_langs:
- C++
helpviewer_keywords:
- shared classes, CSimpleStringT
- strings [C++], ATL class
- CSimpleStringT class
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 791b9ec18cc71fe19f633c12afdc48c835c2bf14
ms.lasthandoff: 02/24/2017

---
# <a name="csimplestringt-class"></a>CSimpleStringT-Klasse
Diese Klasse stellt ein `CSimpleStringT` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename BaseType>
class CSimpleStringT
```  
  
### <a name="parameters"></a>Parameter  
 `BaseType`  
 Der Typ der String-Klasse. Einer der folgenden Werte ist möglich:  
  
- `char`(für ANSI-Zeichenfolgen).  
  
- `wchar_t`(für Unicode-Zeichenfolgen).  
  
- **TCHAR** (nach ANSI- und Unicode-Zeichenfolgen).  

## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleStringT::PCXSTR](#pcxstr)|Ein Zeiger auf eine Konstante Zeichenfolge.|  
|[CSimpleStringT::PXSTR](#pxstr)|Ein Zeiger auf eine Zeichenfolge.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleStringT::CSimpleStringT](#ctor)|Erstellt `CSimpleStringT` Objekte auf unterschiedliche Weise.|  
|[CSimpleStringT:: ~ CSimpleStringT](#dtor)|Destruktor.|  

  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleStringT::Append](#append)|Fügt eine `CSimpleStringT` zu einem vorhandenen Objekt `CSimpleStringT` Objekt.|  
|[CSimpleStringT::AppendChar](#appendchar)|Fügt ein Zeichen um ein vorhandenes `CSimpleStringT` Objekt.|  
|[CSimpleStringT::CopyChars](#copychars)|Kopiert ein oder mehrere Zeichen in eine andere Zeichenfolge.|  
|[CSimpleStringT::CopyCharsOverlapped](#copycharsoverlapped)|Kopiert ein oder mehrere Zeichen in eine andere Zeichenfolge, die in dem Puffer überlappen.|  
|[CSimpleStringT::Empty](#empty)|Erzwingt, dass eine Zeichenfolge, die eine Länge von&0; (null) haben.|  
|[CSimpleStringT::FreeExtra](#freeextra)|Gibt zusätzliche zuvor vom Zeichenfolgenobjekt belegten Arbeitsspeicher frei.|  
|[CSimpleStringT::GetAllocLength](#getalloclength)|Ruft die zugeordnete Länge ein `CSimpleStringT` Objekt.|  
|[CSimpleStringT::GetAt](#getat)|Gibt das Zeichen an einer bestimmten Position zurück.|  
|[CSimpleStringT::GetBuffer](#getbuffer)|Gibt einen Zeiger auf die Zeichen in einem `CSimpleStringT`.|  
|[CSimpleStringT::GetBufferSetLength](#getbuffersetlength)|Gibt einen Zeiger auf die Zeichen in einem `CSimpleStringT`, auf die angegebene Länge abschneiden.|  
|[CSimpleStringT::GetLength](#getlength)|Gibt die Anzahl der Zeichen in einem `CSimpleStringT` Objekt.|  
|[CSimpleStringT::GetManager](#getmanager)|Ruft die Speicher-Manager von der `CSimpleStringT` Objekt.|  
|[CSimpleStringT::GetString](#getstring)|Ruft die Zeichenfolge ab|  
|[CSimpleStringT::IsEmpty](#isempty)|Tests, ob ein `CSimpleStringT` Objekt keine Zeichen enthält.|  
|[CSimpleStringT::LockBuffer](#lockbuffer)|Deaktiviert die Assemblyverweiszählung und schützt die Zeichenfolge im Puffer.|  
|[CSimpleStringT::Preallocate](#preallocate)|Ordnet eine bestimmte Menge an Arbeitsspeicher für den Zeichenpuffer.|  
|[CSimpleStringT::ReleaseBuffer](#releasebuffer)|Gibt die Steuerung der zurückgegebene Puffer `GetBuffer`.|  
|[CSimpleStringT::ReleaseBufferSetLength](#releasebuffersetlength)|Gibt die Steuerung der zurückgegebene Puffer `GetBuffer`.|  
|[CSimpleStringT::SetAt](#setat)|Legt eine an einer bestimmten Position.|  
|[CSimpleStringT::SetManager](#setmanager)|Legt die Speicher-Manager von einem `CSimpleStringT` Objekt.|  
|[CSimpleStringT::SetString](#setstring)|Legt die Zeichenfolge von einem `CSimpleStringT` Objekt.|  
|[CSimpleStringT::StringLength](#stringlength)|Gibt die Anzahl der Zeichen in der angegebenen Zeichenfolge zurück.|  
|[CSimpleStringT::Truncate](#truncate)|Schneidet die Zeichenfolge, die einer angegebenen Länge.|  
|[CSimpleStringT::UnlockBuffer](#unlockbuffer)|Referenzzähler ermöglicht und die Zeichenfolge im Puffer frei.|  

### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleStringT::operator PCXSTR](#operator_pcxstr)|Greift direkt in gespeicherten Zeichen auf ein `CSimpleStringT` Objekt als Zeichenfolge im C-Format.|  
|[CSimpleStringT::operator\[\]](#operator_at)|Gibt das Zeichen an einer bestimmten Position zurück – Operator Ersetzung für `GetAt`.|  
|[CSimpleStringT::operator +=](#operator_add_eq)|Verkettet eine neue Zeichenfolge am Ende einer vorhandenen Zeichenfolge.|  
|[CSimpleStringT::operator =](#operator_eq)|Weist einen neuen Wert zu einem `CSimpleStringT` Objekt.|  
  
### <a name="remarks"></a>Hinweise  
 `CSimpleStringT`ist die Basisklasse für die verschiedenen Zeichenfolgenklassen, die von Visual C++ unterstützt. Es bietet minimale Unterstützung zur Verwaltung des Arbeitsspeichers der String-Objekt und grundlegende pufferbearbeitung. Erweiterte String-Objekten finden Sie unter [CStringT-Klasse](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpstr.h  


## <a name="a-nameappenda-csimplestringtappend"></a><a name="append"></a>CSimpleStringT::Append
Fügt eine `CSimpleStringT` zu einem vorhandenen Objekt `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
void Append(const CSimpleStringT& strSrc); 
void Append(PCXSTR pszSrc, int nLength); 
void Append(PCXSTR pszSrc);
```  
#### <a name="parameters"></a>Parameter  
 `strSrc`  
 Das `CSimpleStringT` Objekt angefügt werden soll.  
  
 `pszSrc`  
 Ein Zeiger auf eine Zeichenfolge mit den Zeichen angefügt werden soll.  
  
 `nLength`  
 Die Anzahl der anzufügenden Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Anfügen einer vorhandenen `CSimpleStringT` Objekt zu einem anderen `CSimpleStringT` Objekt.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::Append`.  
  
```cpp  
CSimpleString str1(pMgr), str2(pMgr);
str1.SetString(_T("Soccer is"));
str2.SetString(_T(" an elegant game"));
str1.Append(str2);
ASSERT(_tcscmp(str1, _T("Soccer is an elegant game")) == 0);
```
  
##  <a name="a-nameappendchara-csimplestringtappendchar"></a><a name="appendchar"></a>CSimpleStringT::AppendChar
Fügt ein Zeichen um ein vorhandenes `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
void AppendChar(XCHAR ch);
```  
#### <a name="parameters"></a>Parameter  
 *CH*  
 Das Zeichen angefügt werden soll  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie das angegebene Zeichen am Ende einer vorhandenen Anfügen `CSimpleStringT` Objekt.  
  
##  <a name="a-namecopycharsa-csimplestringtcopychars"></a><a name="copychars"></a>CSimpleStringT::CopyChars  
 Kopiert ein oder mehrere Zeichen um ein `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
static void CopyChars(
  XCHAR* pchDest,
  const XCHAR* pchSrc, 
  int nChars) throw();
```  
#### <a name="parameters"></a>Parameter  
 `pchDest`  
 Ein Zeiger auf eine Zeichenfolge.  
  
 `pchSrc`  
 Ein Zeiger auf eine Zeichenfolge mit der zu kopierenden Zeichen.  
  
 `nChars`  
 Die Anzahl der `pchSrc` zu kopierenden Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Kopieren von Zeichen aus `pchSrc` an die `pchDest` Zeichenfolge.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::CopyChars`.  
  
```cpp  
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```
  
##  <a name="a-namecopycharsoverlappeda--csimplestringtcopycharsoverlapped"></a><a name="copycharsoverlapped"></a>CSimpleStringT::CopyCharsOverlapped
Kopiert ein oder mehrere Zeichen um ein `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
static void CopyCharsOverlapped(
  XCHAR* pchDest,
  const XCHAR* pchSrc,
  int nChars) throw(); 
```  
#### <a name="parameters"></a>Parameter  
 `pchDest`  
 Ein Zeiger auf eine Zeichenfolge.  
  
 `pchSrc`  
 Ein Zeiger auf eine Zeichenfolge mit der zu kopierenden Zeichen.  
  
 `nChars`  
 Die Anzahl der `pchSrc` zu kopierenden Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Kopieren von Zeichen aus `pchSrc` an die `pchDest` Zeichenfolge. Im Gegensatz zu `CopyChars`, `CopyCharsOverlapped` bietet eine sichere Methode für das Kopieren von Zeichen Puffern, die möglicherweise überlappen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CSimpleStringT::CopyChars](#copychars), oder der Quellcode für `CSimpleStringT::SetString` (befindet sich im atlsimpstr.h).  
  
##  <a name="a-namectora--csimplestringtcsimplestringt"></a><a name="ctor"></a>CSimpleStringT::CSimpleStringT  
 Erstellt ein `CSimpleStringT`-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
CSimpleStringT(const XCHAR* pchSrc, int nLength, IAtlStringMgr* pStringMgr); 
CSimpleStringT(PCXSTR pszSrc, IAtlStringMgr* pStringMgr); 
CSimpleStringT(const CSimpleStringT& strSrc); 
explicit CSimpleStringT(IAtlStringMgr* pStringMgr) throw(); 
```  
#### <a name="parameters"></a>Parameter  
 `strSrc`  
 Eine vorhandene `CSimpleStringT` Objekt in diese kopiert werden `CSimpleStringT` Objekt.  
  
 `pchSrc`  
 Ein Zeiger auf ein Array von Zeichen Länge `nLength`, nicht Null-terminiert.  
  
 `pszSrc`  
 Eine auf Null endende Zeichenfolge, die in diese kopiert werden `CSimpleStringT` Objekt.  
  
 `nLength`  
 Die Anzahl der Zeichen im `pch`.  
  
 `pStringMgr`  
 Ein Zeiger auf den Speicher-Manager von der `CSimpleStringT` Objekt. Weitere Informationen zu `IAtlStringMgr` und Verwaltung des Arbeitsspeichers für `CSimpleStringT`, finden Sie unter [Speicherverwaltung und CStringT](../memory-management-with-cstringt.md).  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein neues `CSimpleStringT`-Objekt. Da die Konstruktoren die Eingabedaten in neuen reservierten Speicher kopieren, können die Speicher-Ausnahmen führen.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::CSimpleStringT` mithilfe der ATL `typedef``CSimpleString`. `CSimpleString`ist eine häufig verwendete Spezialisierung der Klassenvorlage `CSimpleStringT`.  
  
```cpp  
CSimpleString s1(pMgr);
// Empty string
CSimpleString s2(_T("cat"), pMgr);
// From a C string literal

CSimpleString s3(s2);
// Copy constructor
CSimpleString s4(s2 + _T(" ") + s3);

// From a string expression
CSimpleString s5(_T("xxxxxx"), 6, pMgr);
// s5 = "xxxxxx"   
```

  
##  <a name="a-nameemptya--csimplestringtempty"></a><a name="empty"></a>CSimpleStringT::Empty
Dadurch `CSimpleStringT` Objekt eine leere Zeichenfolge und gibt den Arbeitsspeicher nach Bedarf frei.  
  
### <a name="syntax"></a>Syntax  
  
```  
void Empty() throw();  
```  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Zeichenfolgen: CString-Ausnahmebereinigung](../cstring-exception-cleanup.md).  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::Empty`.  
  
```cpp  
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());  
```  
  
##  <a name="a-namefreeextraa--csimplestringtfreeextra"></a><a name="freeextra"></a>CSimpleStringT::FreeExtra
Die Zeichenfolge zuvor zugeordnet, aber nicht mehr benötigt zusätzlichen Speicher frei.  
  
### <a name="syntax"></a>Syntax  
  
```  
void FreeExtra(); 
```  
### <a name="remarks"></a>Hinweise  
 Dies sollte den Speicher-Overhead durch das String-Objekt reduzieren. Die Methode ordnet den Puffer, die genaue Länge [GetLength](#getlength).  
  
### <a name="example"></a>Beispiel  
```cpp  
CAtlString basestr;
IAtlStringMgr* pMgr;

pMgr= basestr.GetManager();
ASSERT(pMgr != NULL);

// Create a CSimpleString with 28 characters
CSimpleString str(_T("Many sports are fun to play."), 28, pMgr);
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// Assigning a smaller string won't cause CSimpleString to free its 
// memory, because it assumes the string will grow again anyway.
str = _T("Soccer is best!");
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());

// This call forces CSimpleString to release the extra 
// memory it doesn't need.
str.FreeExtra();
_tprintf_s(_T("Alloc length is %d, String length is %d\n"),
   str.GetAllocLength(), str.GetLength());
```
  
### <a name="remarks"></a>Hinweise  
 Die Ausgabe dieses Beispiels lautet wie folgt:  
  
 `Alloc length is 1031, String length is 1024`  
  
 `Alloc length is 1031, String length is 15`  
  
 `Alloc length is 15, String length is 15`  
  
##  <a name="a-namegetalloclengtha--csimplestringtgetalloclength"></a><a name="getalloclength"></a>CSimpleStringT::GetAllocLength  
Ruft die zugeordnete Länge ein `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
int GetAllocLength() const throw();  
```  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen, die für dieses Objekt zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Ermitteln der Anzahl von Zeichen, die für diese zugeordneten `CSimpleStringT` Objekt. Finden Sie unter [FreeExtra](#freeextra) ein Beispiel für diese Funktion aufzurufen.  
  
##  <a name="a-namegetata--csimplestringtgetat"></a><a name="getat"></a>CSimpleStringT::GetAt  
Gibt ein Zeichen aus einem `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
XCHAR GetAt(int iChar) const;
```  
#### <a name="parameters"></a>Parameter  
 `iChar`  
 Nullbasierte Index des Zeichens in der `CSimpleStringT` Objekt. Die `iChar` Parameter muss größer als oder gleich 0 und kleiner als der von zurückgegebene Wert [GetLength](#getlength). Andernfalls `GetAt` wird eine Ausnahme generiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine `XCHAR` , die das Zeichen an der angegebenen Position in der Zeichenfolge enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um zurückzugeben, die ein Zeichen, die durch angegebene `iChar`. Der überladene Index (`[]`)-Operator ist ein bequemer Alias für `GetAt`. Der null-Terminator ist ohne Auslösen einer Ausnahme mit adressierbar `GetAt`. Es wird jedoch nicht gezählt von `GetLength`, und der zurückgegebene Wert ist 0.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie `CSimpleStringT::GetAt`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```
  
##  <a name="a-namegetbuffera--csimplestringtgetbuffer"></a><a name="getbuffer"></a>CSimpleStringT::GetBuffer  
Gibt einen Zeiger auf den internen Zeichenpuffer für die `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
PXSTR GetBuffer(int nMinBufferLength); 
PXSTR GetBuffer();
```  
#### <a name="parameters"></a>Parameter  
 `nMinBufferLength`  
 Die minimale Anzahl von Zeichen, die der Zeichenpuffer enthalten kann. Dieser Wert beinhaltet keinen Platz für eine null-Terminator.  
  
 Wenn `nMinBufferLength` ist größer als die Länge des aktuellen Puffers `GetBuffer` zerstört die aktuellen Puffer und ersetzt ihn durch einen Puffer mit der angeforderten Größe der Verweiszähler des Objekts auf&0; (null) zurückgesetzt. Wenn Sie zuvor aufgerufen haben [LockBuffer](#lockbuffer) für diesen Puffer, verlieren Sie die Sperre des Puffers.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `PXSTR` Zeiger auf das Objekt (Null) endende Puffer.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um den Inhalt des Puffers des Zurückgeben der `CSimpleStringT` Objekt. Das zurückgegebene `PXSTR` ist keine Konstante und ermöglicht daher direkte Änderung von `CSimpleStringT` Inhalt.  
  
 Bei Verwendung den zurückgegebene Zeiger `GetBuffer` um den Inhalt der Zeichenfolge zu ändern, müssen Sie aufrufen [ReleaseBuffer](#releasebuffer) vor der Verwendung einer anderen `CSimpleStringT` Membermethoden.  
  
 Die zurückgegebene Adresse `GetBuffer` ist unzulässig nach dem Aufruf von `ReleaseBuffer` da zusätzliche `CSimpleStringT` kann dazu führen, dass die `CSimpleStringT` Puffer neu reserviert werden. Der Puffer wird nicht neu zugewiesen, wenn Sie nicht die Länge der Ändern der `CSimpleStringT`.  
  
 Der Arbeitsspeicherpuffer wird automatisch freigegeben wird, wenn die `CSimpleStringT` -Objekt zerstört wird.  
  
 Wenn Sie die Länge der Zeichenfolge selbst mitverfolgen, sollten Sie nicht das abschließende Nullzeichen anhängen. Sie müssen jedoch die endgültige Zeichenfolgenlänge angeben, wenn Sie den Puffer mit freigeben `ReleaseBuffer`. Wenn Sie ein abschließendes Nullzeichen anfügen, sollten Sie –&1; (Standard) für die Länge übergeben. `ReleaseBuffer`dann bestimmt die Länge des Puffers.  
  
 Wenn nicht genügend zum erfüllen Speicher der `GetBuffer` anfordern, löst diese Methode eine CMemoryException *.  
  
### <a name="example"></a>Beispiel  
```cpp  
CSimpleString s(_T("abcd"), pMgr);
LPTSTR pBuffer = s.GetBuffer(10);
int sizeOfBuffer = s.GetAllocLength();

// Directly access CSimpleString buffer
_tcscpy_s(pBuffer, sizeOfBuffer, _T("Hello"));
ASSERT(_tcscmp(s, _T("Hello")) == 0);
s.ReleaseBuffer();   
```
  
##  <a name="a-namegetbuffersetlengtha--csimplestringtgetbuffersetlength"></a><a name="getbuffersetlength"></a>CSimpleStringT::GetBufferSetLength  
Gibt einen Zeiger auf den internen Zeichenpuffer für die `CSimpleStringT` Objekt abschneiden oder seine Länge wächst, ggf. genau die in angegebene Länge `nLength`.  
  
### <a name="syntax"></a>Syntax  
  
```  
PXSTR GetBufferSetLength(int nLength);
```  
#### <a name="parameters"></a>Parameter  
 `nLength`  
 Die genaue Größe des dem `CSimpleStringT` Zeichenpuffer in Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `PXSTR` Zeiger auf das Objekt (Null) endende Puffer.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen einer angegebenen Länge von den internen Puffer von der `CSimpleStringT` Objekt. Das zurückgegebene `PXSTR` -Zeiger ist nicht `const` und auf diese Weise direkte Änderung von `CSimpleStringT` Inhalt.  
  
 Bei Verwendung den zurückgegebene Zeiger [GetBufferSetLength](#getbuffersetlength) aufrufen, um den Inhalt der Zeichenfolge zu ändern, `ReleaseBuffer` aktualisieren Sie den internen Zustand des `CsimpleStringT` vor der Verwendung einer anderen `CSimpleStringT` Methoden.  
  
 Die zurückgegebene Adresse `GetBufferSetLength` ist unzulässig nach dem Aufruf von `ReleaseBuffer` da zusätzliche `CSimpleStringT` kann dazu führen, dass die `CSimpleStringT` Puffer neu reserviert werden. Der Puffer nicht erneut zugewiesen, wenn Sie nicht die Länge der Ändern der `CSimpleStringT`.  
  
 Der Arbeitsspeicherpuffer wird automatisch freigegeben wird, wenn die `CSimpleStringT` -Objekt zerstört wird.  
  
 Wenn Sie die Länge der Zeichenfolge selbst mitverfolgen, nicht fügen Sie keine das abschließende Nullzeichen. Geben Sie die Länge der endgültigen Zeichenfolge beim Freigeben des Puffers mit `ReleaseBuffer`. Wenn Sie ein abschließendes Nullzeichen anfügen beim Aufruf von `ReleaseBuffer`, übergeben Sie –&1; (Standard) für die Länge, die `ReleaseBuffer`, und `ReleaseBuffer` führt eine `strlen` in den Puffer, der die Länge.  
  
 Weitere Informationen zum zählen der Verweise finden Sie unter den folgenden Artikeln:  
  
- [Verwalten der Objektlebensdauern über Referenzzähler](http://msdn.microsoft.com/library/windows/desktop/ms687260) im Windows SDK. 
  
- [Implementieren von Referenzzähler](http://msdn.microsoft.com/library/windows/desktop/ms693431) im Windows SDK.
  
- [Regeln für die Verwaltung von Verweiszähler](http://msdn.microsoft.com/library/windows/desktop/ms692481) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::GetBufferSetLength`.  
  
```cpp  
CSimpleString str(pMgr);
LPTSTR pstr = str.GetBufferSetLength(3);
pstr[0] = _T('C');
pstr[1] = _T('u');
pstr[2] = _T('p');

// No need for trailing zero or call to ReleaseBuffer() 
// because GetBufferSetLength() set it for us.

str += _T(" soccer is best!");
ASSERT(_tcscmp(str, _T("Cup soccer is best!")) == 0);
```
  
##  <a name="a-namegetlengtha--csimplestringtgetlength"></a><a name="getlength"></a>CSimpleStringT::GetLength  
Gibt die Anzahl der Zeichen in der `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
int GetLength() const throw();  
```  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen in der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Anzahl der Zeichen in dem Objekt zurückzugeben. Die Anzahl die enthält einen null-Terminator keine.  
  
 Für Mehrbyte-Zeichensätzen (MBCS) setzt `GetLength` zählt jedes 8-Bit-Zeichen, d. h. ein und die nachfolgenden Byte in einem Multibyte-Zeichen als zwei Bytes gezählt werden. Finden Sie unter [FreeExtra](#freeextra) ein Beispiel für diese Funktion aufzurufen.  
  
##  <a name="a-namegetmanagera--csimplestringtgetmanager"></a><a name="getmanager"></a>CSimpleStringT::GetManager  
Ruft die Speicher-Manager von der `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
IAtlStringMgr* GetManager() const throw();  
```  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Speichermanager für die `CSimpleStringT` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen des Speichers-Manager verwendet werden, indem die `CSimpleStringT` Objekt. Weitere Informationen zu Speicher-Manager und String-Objekten finden Sie unter [Speicherverwaltung und CStringT](../memory-management-with-cstringt.md).  
  
##  <a name="a-namegetstringa--csimplestringtgetstring"></a><a name="getstring"></a>CSimpleStringT::GetString
Ruft die Zeichenfolge ab.  
  
### <a name="syntax"></a>Syntax  
  
```  
PCXSTR GetString() const throw();
```  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen von zugeordneten Zeichenfolge die `CSimpleStringT` Objekt.  
  
> [!NOTE]
>  Das zurückgegebene `PCXSTR` Zeiger `const` und lässt keine direkte Änderung von `CSimpleStringT` Inhalt.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::GetString`.  
  
```cpp  
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```
  
##  <a name="a-nameisemptya--csimplestringtisempty"></a><a name="isempty"></a>CSimpleStringT::IsEmpty  
Tests ein `CSimpleStringT` Objekt für die leere Bedingung.  
  
### <a name="syntax"></a>Syntax  
  
```  
bool IsEmpty() const throw();  
```  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** Wenn das `CSimpleStringT` Objekt hat die Länge 0 andernfalls **false**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um zu bestimmen, ob das Objekt eine leere Zeichenfolge enthält.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::IsEmpty`.  
  
```cpp  
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```
  
##  <a name="a-namelockbuffera--csimplestringtlockbuffer"></a><a name="lockbuffer"></a>CSimpleStringT::LockBuffer  
Deaktiviert die Assemblyverweiszählung und schützt die Zeichenfolge im Puffer.  
  
### <a name="syntax"></a>Syntax  
  
```  
PXSTR LockBuffer();
```  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein `CSimpleStringT` Objekt oder eine auf Null endende Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um den Puffer zu sperren, die `CSimpleStringT` Objekt. Durch Aufrufen von `LockBuffer`, Sie erstellen eine Kopie der Zeichenfolge mit-1 für den Verweiszähler. Wenn die Verweisanzahl den Wert-1 ist, gilt die Zeichenfolge im Puffer "gesperrt" sein. Die Zeichenfolge wird in einen gesperrten Zustand auf zwei Arten geschützt:  
  
-   Keine andere Zeichenfolge erhalten einen Verweis auf die Daten in der Zeichenfolge mit gesperrten, auch wenn diese Zeichenfolge an die gesperrte Zeichenfolge zugeordnet ist.  
  
-   Die gesperrte Zeichenfolge verweist nie eine andere Zeichenfolge, selbst wenn die andere Zeichenfolge an die gesperrte Zeichenfolge kopiert wird.  
  
 Sperren Sie die Zeichenfolge im Puffer, stellen Sie sicher, dass die Zeichenfolge exklusiven im Puffer intakt bleibt.  
  
 Klicken Sie nach mit `LockBuffer`, rufen Sie [UnlockBuffer](#unlockbuffer) den Verweiszähler auf 1 zurückgesetzt.  
  
> [!NOTE]
>  Wenn Sie aufrufen [GetBuffer](#getbuffer) auf einen gesperrten Puffer und Sie legen die `GetBuffer` Parameter `nMinBufferLength` größer als die Länge des aktuellen Puffers, verlieren Sie die Sperre des Puffers. Solch ein Aufruf an `GetBuffer` zerstört die aktuellen Puffer und ersetzt ihn durch einen Puffer mit der angeforderten Größe wird den Verweiszähler auf&0; (null) zurückgesetzt.  
  
 Weitere Informationen zum zählen der Verweise finden Sie unter den folgenden Artikeln:  
  
- [Verwalten der Objektlebensdauern über Referenzzähler](http://msdn.microsoft.com/library/windows/desktop/ms687260) im Windows SDK  
  
- [Implementieren von Referenzzähler](http://msdn.microsoft.com/library/windows/desktop/ms693431) im Windows SDK  
  
- [Regeln für die Verwaltung von Verweiszähler](http://msdn.microsoft.com/library/windows/desktop/ms692481) im Windows SDK  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::LockBuffer`.  
  
```cpp  
CSimpleString str(_T("Hello"), pMgr);
TCHAR ch;

str.LockBuffer();
ch = str.GetAt(2);
_tprintf_s(_T("%c"), ch);
str.UnlockBuffer();
```
  
##  <a name="a-nameoperatorata--csimplestringtoperator"></a><a name="operator_at"></a>CSimpleStringT::operator\[\]  
Rufen Sie diese Funktion für den Zugriff auf ein einzelnes Zeichen als Zeichenarray.  
  
### <a name="syntax"></a>Syntax  
  
```  
XCHAR operator[](int iChar) const;
```  
#### <a name="parameters"></a>Parameter  
 `iChar`  
 Nullbasierten Index eines Zeichens in der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Der überladene Index (`[]`) Operator gibt ein einzelnes Zeichen, die von der nullbasierte Index im angegebenen `iChar`. Dieser Operator ist eine praktische Ersatz für die [GetAt](#getat) Member-Funktion.  
  
> [!NOTE]
>  Können Sie den Index (`[]`) Operator, um den Nutzen eines Zeichens in einer `CSimpleStringT`, aber Sie können es ändern Sie den Wert eines Zeichens in einer `CSimpleStringT`.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von **CSimpleStringT::operator []**.  
  
```cpp  
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```
  
## <a name="a-nameoperatorata--csimplestringtoperator-"></a><a name="operator_at"></a>CSimpleStringT::operator\[\]
Rufen Sie diese Funktion für den Zugriff auf ein einzelnes Zeichen als Zeichenarray.  
  
### <a name="syntax"></a>Syntax  
  
```   
XCHAR operator[](int iChar) const;
```  
  
### <a name="parameters"></a>Parameter  
 `iChar`  
 Nullbasierten Index eines Zeichens in der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Der überladene Index (`[]`) Operator gibt ein einzelnes Zeichen, die von der nullbasierte Index im angegebenen `iChar`. Dieser Operator ist eine praktische Ersatz für die [GetAt](#getat) Member-Funktion.  
  
> [!NOTE]
>  Können Sie den Index (`[]`) Operator, um den Nutzen eines Zeichens in einer `CSimpleStringT`, aber Sie können es ändern Sie den Wert eines Zeichens in einer `CSimpleStringT`.  
  
  
##  <a name="a-nameoperatoraddeqa--csimplestringtoperator-"></a><a name="operator_add_eq"></a>CSimpleStringT::operator +=  
Verknüpft eine neue Zeichenfolge oder ein Zeichen am Ende einer vorhandenen Zeichenfolge.  
  
### <a name="syntax"></a>Syntax  
  
```  
CSimpleStringT& operator +=(PCXSTR pszSrc); 
CSimpleStringT& operator +=(const CSimpleStringT& strSrc); 
template<int t_nSize>  
CSimpleStringT& operator+=(const CStaticString< XCHAR, t_nSize >& strSrc); 
CSimpleStringT& operator +=(char ch); 
CSimpleStringT& operator +=(unsigned char ch); 
CSimpleStringT& operator +=(wchar_t ch);
```  
#### <a name="parameters"></a>Parameter  
 `pszSrc`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge.  
  
 `strSrc`  
 Ein Zeiger auf ein vorhandenes `CSimpleStringT` Objekt.  
  
 *CH*  
 Das Zeichen, das angefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Der Operator akzeptiert ein anderes `CSimpleStringT` Objekt oder ein Zeichen. Beachten Sie, dass der Speicher Ausnahmen auftreten, wenn Sie diese Verkettungsoperator verwenden, da es sich bei neuer Speicher für diese hinzugefügten Zeichen zugeordnet werden kann `CSimpleStringT` Objekt.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von **CSimpleStringT::operator +=**.  
  
```cpp  
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```
  
##  <a name="a-nameoperatoreqa--csimplestringtoperator-"></a><a name="operator_eq"></a>CSimpleStringT::operator =  
Weist einen neuen Wert zu einem `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
CSimpleStringT& operator =(PCXSTR pszSrc); 
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```  
#### <a name="parameters"></a>Parameter  
 `pszSrc`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge.  
  
 `strSrc`  
 Ein Zeiger auf ein vorhandenes `CSimpleStringT` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Zielzeichenfolge (links) groß genug ist, um die neuen Daten zu speichern ist, wird keine neue speicherbelegung ausgeführt. Beachten Sie, dass der Speicher Ausnahmen auftreten, bei jeder Verwendung den Zuweisungsoperator, da häufig neuer Speicher zugeordnet ist, enthält das resultierende `CSimpleStringT` Objekt.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von **CSimpleStringT::operator =**.  
  
```cpp  
CSimpleString s1(pMgr), s2(pMgr);
// Empty CSimpleStringT objects

s1 = _T("cat");
// s1 = "cat"
ASSERT(_tcscmp(s1, _T("cat")) == 0);

s2 = s1;               // s1 and s2 each = "cat"
ASSERT(_tcscmp(s2, _T("cat")) == 0);

s1 = _T("the ") + s1;      
// Or expressions
ASSERT(_tcscmp(s1, _T("the cat")) == 0);

s1 = _T("x");
// Or just individual characters
ASSERT(_tcscmp(s1, _T("x")) == 0);
```
  
##  <a name="a-nameoperatorpcxstra--csimplestringtoperator-pcxstr"></a><a name="operator_pcxstr"></a>CSimpleStringT::operator PCXSTR  

 Greift direkt in gespeicherten Zeichen auf ein `CSimpleStringT` Objekt als Zeichenfolge im C-Format.  
  
### <a name="syntax"></a>Syntax  
  
```  
operator PCXSTR() const throw();
```  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeichenzeiger von der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Es werden keine Zeichen kopiert. nur ein Zeiger zurückgegeben. Achten Sie darauf, dass mit diesem Operator. Wenn Sie ändern eine `CString` Objekt, nachdem Sie die Zeichenzeiger erhalten haben, verursachen Sie vielleicht ein erneutes Zuweisen von Arbeitsspeicher, der den Zeiger ungültig.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von **CSimpleStringT::operator PCXSTR**.  
  
```cpp  
// If the prototype of a function is known to the compiler, 
// the PCXSTR cast operator may be invoked implicitly.

CSimpleString strSports(L"Soccer is Best!", pMgr);
WCHAR sz[1024];

wcscpy_s(sz, strSports);

// If the prototype isn't known or is a va_arg prototype, 
// you must invoke the cast operator explicitly. For example, 
// the va_arg part of a call to swprintf_s() needs the cast:

swprintf_s(sz, 1024, L"I think that %s!\n", (PCWSTR)strSports);

// While the format parameter is known to be an PCXSTR and 
// therefore doesn't need the cast:

swprintf_s(sz, 1024, strSports);

// Note that some situations are ambiguous. This line will 
// put the address of the strSports object to stdout:

wcout << strSports;

// while this line will put the content of the string out:

wcout << (PCWSTR)strSports;   
``` 
  
##  <a name="a-namepcxstra--csimplestringtpcxstr"></a><a name="pcxstr"></a>CSimpleStringT::PCXSTR
Ein Zeiger auf eine Konstante Zeichenfolge.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;    
```  
##  <a name="a-namepreallocatea--csimplestringtpreallocate"></a><a name="preallocate"></a>CSimpleStringT::Preallocate  
Ordnet eine bestimmte Menge von Bytes für den `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
void Preallocate( int nLength);
```  
#### <a name="parameters"></a>Parameter  
 `nLength`  
 Die genaue Größe des dem `CSimpleStringT` Zeichenpuffer in Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um eine bestimmte Puffergröße für Zuordnen der `CSimpleStringT` Objekt.  
  
 `CSimpleStringT`generiert eine `STATUS_NO_MEMORY` -Ausnahme aus, wenn sie Speicherplatz für den Zeichenpuffer zugewiesen werden kann. Standardmäßig erfolgt die speicherbelegung von Win32-API-Funktionen `HeapAlloc` oder `HeapReAlloc`.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::Preallocate`.  
  
```cpp  
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```
  
##  <a name="a-namepxstra--csimplestringtpxstr"></a><a name="pxstr"></a>CSimpleStringT::PXSTR  
Ein Zeiger auf eine Zeichenfolge.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;  
```  
##  <a name="a-namereleasebuffera--csimplestringtreleasebuffer"></a><a name="releasebuffer"></a>CSimpleStringT::ReleaseBuffer  
Gibt die Steuerung der Puffer [GetBuffer](#getbuffer).  
  
### <a name="syntax"></a>Syntax  
  
```  
void ReleaseBuffer(int nNewLength = -1);
```  
#### <a name="parameters"></a>Parameter  
 `nNewLength`  
 Die neue Länge der Zeichenfolge in Zeichen, ohne Berücksichtigung von null-Terminator. Wenn die Zeichenfolge null beendet ist, der Standardwert-1 legt die `CSimpleStringT` auf die aktuelle Länge der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um neu zuordnen, oder geben Sie den Puffer mit dem String-Objekt. Wenn Sie wissen, dass die Zeichenfolge im Puffer Null-terminiert ist, können Sie weglassen der `nNewLength` Argument. Wenn die Zeichenfolge nicht null ist, beendet, verwenden Sie `nNewLength` seine Länge angeben. Die zurückgegebene Adresse [GetBuffer](#getbuffer) ungültig ist, nach dem Aufruf von `ReleaseBuffer` oder andere `CSimpleStringT` Vorgang.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::ReleaseBuffer`.  
  
```cpp  
const int bufferSize = 1024;
CSimpleString s(_T("abc"), pMgr);
LPTSTR p = s.GetBuffer(bufferSize);
_tcscpy_s(p, bufferSize, _T("abc"));

  // use the buffer directly
ASSERT(s.GetLength() == 3);

// String length = 3
s.ReleaseBuffer();

// Surplus memory released, p is now invalid.
ASSERT(s.GetLength() == 3);

// Length still 3
```
  
##  <a name="a-namereleasebuffersetlengtha--csimplestringtreleasebuffersetlength"></a><a name="releasebuffersetlength"></a>CSimpleStringT::ReleaseBufferSetLength

Gibt die Steuerung der Puffer [GetBuffer](#getbuffer).  
  
### <a name="syntax"></a>Syntax  
  
```  
void ReleaseBufferSetLength(int nNewLength);
```  
#### <a name="parameters"></a>Parameter  
 `nNewLength`  
 Die Länge der Zeichenfolge freigegeben wird  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist funktional mit [ReleaseBuffer](#releasebuffer) mit dem Unterschied, dass eine gültige Länge für das String-Objekt übergeben werden muss.  
  
##  <a name="a-namesetata--csimplestringtsetat"></a><a name="setat"></a>CSimpleStringT::SetAt  
Legt ein einzelnes Zeichen aus einem `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
void SetAt(int iChar, XCHAR ch);
```  
#### <a name="parameters"></a>Parameter  
 `iChar`  
 Nullbasierte Index des Zeichens in der `CSimpleStringT` Objekt. Die `iChar` Parameter muss größer als oder gleich 0 und kleiner als der von zurückgegebene Wert [GetLength](#getlength).  
  
 *CH*  
 Das neue Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Überschreiben des Zeichens an `iChar`. Diese Methode wird die Zeichenfolge nicht vergrößern, wenn `iChar` überschreitet die Grenzen der bestehende Zeichenfolge.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::SetAt`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
``` 
  
##  <a name="a-namesetmanagera--csimplestringtsetmanager"></a><a name="setmanager"></a>CSimpleStringT::SetManager  
Gibt den Speichermanager von der `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
void SetManager(IAtlStringMgr* pStringMgr);
```  
#### <a name="parameters"></a>Parameter  
 `pStringMgr`  
 Ein Zeiger auf den neuen Speichermanager.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Angeben eines neuen Speichers-Manager verwendet werden, indem die `CSimpleStringT` Objekt. Weitere Informationen zu Speicher-Manager und String-Objekten finden Sie unter [Speicherverwaltung und CStringT](../memory-management-with-cstringt.md).  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::SetManager`.  
  
```cpp  
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```
  
##  <a name="a-namesetstringa--csimplestringtsetstring"></a><a name="setstring"></a>CSimpleStringT::SetString  
Legt die Zeichenfolge von einem `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
void SetString(PCXSTR pszSrc, int nLength); 
void SetString(PCXSTR pszSrc);
```  
#### <a name="parameters"></a>Parameter  
 `pszSrc`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge.  
  
 `nLength`  
 Die Anzahl der Zeichen im `pszSrc`.  
  
### <a name="remarks"></a>Hinweise  
 Kopieren Sie eine Zeichenfolge in der `CSimpleStringT` Objekt. `SetString`überschreibt die ältere Zeichenfolgendaten in den Puffer.  
  
 Beide Versionen des `SetString` überprüfen, ob `pszSrc` null-Zeiger und auszulösen, wenn dies der Fall, ein **E_INVALIDARG** Fehler.  
  
 Die Version für einen Parameter des `SetString` erwartet, dass `pszSrc` auf Null endende Zeichenfolge.  
  
 Die beiden Parameter Version des `SetString` auch erwartet, dass `pszSrc` eine Null-terminierte Zeichenfolge sein. Er verwendet `nLength` als die Länge der Zeichenfolge, wenn ein null-Terminator das erste Mal auftritt.  
  
 Die beiden Parameter Version des `SetString` überprüft auch, ob `pszSrc` verweist auf eine Position im aktuellen Puffer `CSimpleStringT`. In diesem speziellen Fall `SetString` verwendet eine Funktion zum Kopieren von Arbeitsspeicher, die nicht die Zeichenfolgendaten überschrieben wird, wie die Zeichenfolgendaten zurück in den Puffer kopiert.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::SetString`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```
  
##  <a name="a-namestringlengtha--csimplestringtstringlength"></a><a name="stringlength"></a>CSimpleStringT::StringLength  
Gibt die Anzahl der Zeichen in der angegebenen Zeichenfolge zurück.  
  
### <a name="syntax"></a>Syntax  
  
```  
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```  
#### <a name="parameters"></a>Parameter  
 `psz`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen in `psz`; ohne Berücksichtigung von null-Terminator.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen der Anzahl der Zeichen in der Zeichenfolge, die auf den `psz`.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::StringLength`.  
  
```cpp  
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
``` 
  
##  <a name="a-nametruncatea--csimplestringttruncate"></a><a name="truncate"></a>CSimpleStringT::Truncate
Schneidet die Zeichenfolge, die die neue Länge ab.  
  
### <a name="syntax"></a>Syntax  
  
```  
void Truncate(int nNewLength);
```  
#### <a name="parameters"></a>Parameter  
 `nNewLength`  
 Die neue Länge der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um den Inhalt der Zeichenfolge, die die neue Länge abgeschnitten.  
  
> [!NOTE]
>  Dies wirkt sich nicht auf die zugeordnete Länge des Puffers. Zum Vergrößern oder den aktuellen Puffer zu erhöhen, finden Sie unter [FreeExtra](#freeextra) und [Preallocate](#preallocate).  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::Truncate`.  
  
```cpp  
CSimpleString str(_T("abcdefghi"), pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
str.Truncate(4);
_tprintf_s(_T("Allocated length: %d\n"), str.GetLength());
_tprintf_s(_T("Contents: %s\n"), str);
``` 
  
##  <a name="a-nameunlockbuffera--csimplestringtunlockbuffer"></a><a name="unlockbuffer"></a>CSimpleStringT::UnlockBuffer
 Entsperrt den Puffer mit den `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
void UnlockBuffer() throw();
```  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um den Verweiszähler der Zeichenfolge auf 1 zurückgesetzt.  
  
 Die `CSimpleStringT` Destruktors automatisch `UnlockBuffer` um sicherzustellen, dass der Puffer nicht gesperrt ist, wenn der Destruktor aufgerufen wird. Ein Beispiel für diese Methode, finden Sie unter [LockBuffer](#lockbuffer).  
  
##  <a name="a-namedtora--csimplestringtcsimplestringt"></a><a name="dtor"></a>CSimpleStringT:: ~ CSimpleStringT
Zerstört ein `CSimpleStringT`-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
~CSimpleStringT() throw();
```  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zerstört die `CSimpleStringT` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL/MFC-freigegeben Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)
