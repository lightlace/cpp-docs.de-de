---
title: CSimpleStringT Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT::PCXSTR
- ATLSIMPSTR/ATL::CSimpleStringT::PXSTR
- ATLSIMPSTR/ATL::CSimpleStringT::CSimpleStringT
- ATLSIMPSTR/ATL::CSimpleStringT::Append
- ATLSIMPSTR/ATL::CSimpleStringT::AppendChar
- ATLSIMPSTR/ATL::CSimpleStringT::CopyChars
- ATLSIMPSTR/ATL::CSimpleStringT::CopyCharsOverlapped
- ATLSIMPSTR/ATL::CSimpleStringT::Empty
- ATLSIMPSTR/ATL::CSimpleStringT::FreeExtra
- ATLSIMPSTR/ATL::CSimpleStringT::GetAllocLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetAt
- ATLSIMPSTR/ATL::CSimpleStringT::GetBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::GetBufferSetLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetLength
- ATLSIMPSTR/ATL::CSimpleStringT::GetManager
- ATLSIMPSTR/ATL::CSimpleStringT::GetString
- ATLSIMPSTR/ATL::CSimpleStringT::IsEmpty
- ATLSIMPSTR/ATL::CSimpleStringT::LockBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::Preallocate
- ATLSIMPSTR/ATL::CSimpleStringT::ReleaseBuffer
- ATLSIMPSTR/ATL::CSimpleStringT::ReleaseBufferSetLength
- ATLSIMPSTR/ATL::CSimpleStringT::SetAt
- ATLSIMPSTR/ATL::CSimpleStringT::SetManager
- ATLSIMPSTR/ATL::CSimpleStringT::SetString
- ATLSIMPSTR/ATL::CSimpleStringT::StringLength
- ATLSIMPSTR/ATL::CSimpleStringT::Truncate
- ATLSIMPSTR/ATL::CSimpleStringT::UnlockBuffer
dev_langs:
- C++
helpviewer_keywords:
- shared classes, CSimpleStringT
- strings [C++], ATL class
- CSimpleStringT class
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7dc68cd1d91cb7b651dbeb68422f6a89fb9f2f8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366561"
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
 Der Typ der Zeichenfolgenklasse. Einer der folgenden Werte ist möglich:  
  
- `char` (für ANSI-Zeichenfolgen).  
  
- `wchar_t` (für Unicode-Zeichenfolgen).  
  
- **TCHAR** (für ANSI- und Unicode-Zeichenfolgen).  

## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleStringT::PCXSTR](#pcxstr)|Ein Zeiger auf eine Konstante Zeichenfolge.|  
|[CSimpleStringT::PXSTR](#pxstr)|Ein Zeiger auf eine Zeichenfolge.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleStringT::CSimpleStringT](#ctor)|Erstellt `CSimpleStringT` Objekte auf verschiedene Weise.|  
|[CSimpleStringT:: ~ CSimpleStringT](#dtor)|Destruktor.|  

  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleStringT::Append](#append)|Fügt eine `CSimpleStringT` zu einem vorhandenen Objekt `CSimpleStringT` Objekt.|  
|[CSimpleStringT::AppendChar](#appendchar)|Fügt ein Zeichen zu einem vorhandenen `CSimpleStringT` Objekt.|  
|[CSimpleStringT::CopyChars](#copychars)|Kopiert ein oder mehrere Zeichen in eine andere Zeichenfolge an.|  
|[CSimpleStringT::CopyCharsOverlapped](#copycharsoverlapped)|Kopiert ein oder mehrere Zeichen in eine andere Zeichenfolge, die in der die Puffer, die sich überschneiden.|  
|[CSimpleStringT::Empty](#empty)|Erzwingt, dass eine Zeichenfolge, die eine Länge von 0 (null) haben.|  
|[CSimpleStringT::FreeExtra](#freeextra)|Gibt alle zusätzlichen Speicherplatz, der zuvor von der String-Objekt zugeordnet.|  
|[CSimpleStringT::GetAllocLength](#getalloclength)|Ruft die zugeordnete Länge einer `CSimpleStringT` Objekt.|  
|[CSimpleStringT::GetAt](#getat)|Gibt das Zeichen an der angegebenen Position zurück.|  
|[CSimpleStringT::GetBuffer](#getbuffer)|Gibt einen Zeiger auf die Zeichen in einem `CSimpleStringT`.|  
|[CSimpleStringT::GetBufferSetLength](#getbuffersetlength)|Gibt einen Zeiger auf die Zeichen in einem `CSimpleStringT`, Abschneiden der angegebenen Länge.|  
|[CSimpleStringT::GetLength](#getlength)|Gibt die Anzahl der Zeichen in einem `CSimpleStringT` Objekt.|  
|[CSimpleStringT::GetManager](#getmanager)|Ruft ab, der Speicher-Manager, der die `CSimpleStringT` Objekt.|  
|[CSimpleStringT::GetString](#getstring)|Ruft die Zeichenfolge ab|  
|[CSimpleStringT::IsEmpty](#isempty)|Tests, ob ein `CSimpleStringT` Objekt keine Zeichen enthält.|  
|[CSimpleStringT::LockBuffer](#lockbuffer)|Deaktiviert die verweiszählung, und schützt die Zeichenfolge im Puffer.|  
|[CSimpleStringT::Preallocate](#preallocate)|Ordnet eine bestimmte Menge an Arbeitsspeicher für der Zeichenpuffer.|  
|[CSimpleStringT::ReleaseBuffer](#releasebuffer)|Gibt die Steuerung des Puffers zurückgegebenes frei `GetBuffer`.|  
|[CSimpleStringT::ReleaseBufferSetLength](#releasebuffersetlength)|Gibt die Steuerung des Puffers zurückgegebenes frei `GetBuffer`.|  
|[CSimpleStringT::SetAt](#setat)|Legt ein Zeichen an der angegebenen Position fest.|  
|[CSimpleStringT::SetManager](#setmanager)|Legt die Speicher-Manager von einem `CSimpleStringT` Objekt.|  
|[CSimpleStringT::SetString](#setstring)|Legt die Zeichenfolge von einem `CSimpleStringT` Objekt.|  
|[CSimpleStringT::StringLength](#stringlength)|Gibt die Anzahl der Zeichen in der angegebenen Zeichenfolge zurück.|  
|[CSimpleStringT::Truncate](#truncate)|Schneidet die Zeichenfolge zu einer angegebenen Länge ab.|  
|[CSimpleStringT::UnlockBuffer](#unlockbuffer)|Ermöglicht verweiszählung und die Zeichenfolge im Puffer frei.|  

### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleStringT::operator PCXSTR](#operator_pcxstr)|Greift direkt in gespeicherten Zeichen auf eine `CSimpleStringT` Objekt als Zeichenfolge im C-Format.|  
|[CSimpleStringT::operator\[\]](#operator_at)|Gibt das Zeichen an der angegebenen Position zurück – Operator Ersatz für `GetAt`.|  
|[CSimpleStringT::operator +=](#operator_add_eq)|Verkettet eine neue Zeichenfolge am Ende einer vorhandenen Zeichenfolge an.|  
|[CSimpleStringT::operator =](#operator_eq)|Weist einen neuen Wert zu einem `CSimpleStringT` Objekt.|  
  
### <a name="remarks"></a>Hinweise  
 `CSimpleStringT` ist die Basisklasse für die verschiedenen Zeichenfolgenklassen, die von Visual C++ unterstützt. Es bietet minimale Unterstützung für die Speicherverwaltung von der String-Objekt und grundlegende pufferbearbeitung. Erweiterte Zeichenfolgenobjekten, finden Sie unter [CStringT Class](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpstr.h  


## <a name="append"></a> CSimpleStringT::Append
Fügt eine `CSimpleStringT` zu einem vorhandenen Objekt `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
void Append(const CSimpleStringT& strSrc); 
void Append(PCXSTR pszSrc, int nLength); 
void Append(PCXSTR pszSrc);
```  
#### <a name="parameters"></a>Parameter  
 `strSrc`  
 Die `CSimpleStringT` Objekt angefügt werden.  
  
 `pszSrc`  
 Ein Zeiger auf eine Zeichenfolge, enthält das Zeichen an, die angefügt werden.  
  
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
  
##  <a name="appendchar"></a> CSimpleStringT::AppendChar
Fügt ein Zeichen zu einem vorhandenen `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
void AppendChar(XCHAR ch);
```  
#### <a name="parameters"></a>Parameter  
 *ch*  
 Das Zeichen an, die angefügt werden  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie das angegebene Zeichen am Ende eines vorhandenen Anfügen `CSimpleStringT` Objekt.  
  
##  <a name="copychars"></a> CSimpleStringT::CopyChars  
 Kopiert ein Zeichen oder Zeichen, die eine `CSimpleStringT` Objekt.  
  
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
 Ein Zeiger auf eine Zeichenfolge, die mit den zu kopierenden Zeichen.  
  
 `nChars`  
 Die Anzahl der `pchSrc` zu kopierenden Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Kopieren von Zeichen aus `pchSrc` auf die `pchDest` Zeichenfolge.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::CopyChars`.  
  
```cpp  
CSimpleString str(_T("xxxxxxxxxxxxxxxxxxx"), 20, pMgr);
TCHAR* pszSrc = _T("Hello world!");
_tprintf_s(_T("%s\n"), str);
str.CopyChars(str.GetBuffer(), pszSrc, 12);
_tprintf_s(_T("%s\n"), str);
```
  
##  <a name="copycharsoverlapped"></a>  CSimpleStringT::CopyCharsOverlapped
Kopiert ein Zeichen oder Zeichen, die eine `CSimpleStringT` Objekt.  
  
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
 Ein Zeiger auf eine Zeichenfolge, die mit den zu kopierenden Zeichen.  
  
 `nChars`  
 Die Anzahl der `pchSrc` zu kopierenden Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Kopieren von Zeichen aus `pchSrc` auf die `pchDest` Zeichenfolge. Im Gegensatz zu `CopyChars`, `CopyCharsOverlapped` bietet eine sichere Methode zum Kopieren aus der Zeichenpuffer, die möglicherweise überlappt werden.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CSimpleStringT::CopyChars](#copychars), oder der Quellcode für `CSimpleStringT::SetString` (im Verzeichnis atlsimpstr.h).  
  
##  <a name="ctor"></a>  CSimpleStringT::CSimpleStringT  
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
 Ein Zeiger auf ein Array von Zeichen Länge `nLength`, keine Null-terminiert.  
  
 `pszSrc`  
 Eine auf Null endende Zeichenfolge, die in diese kopiert werden `CSimpleStringT` Objekt.  
  
 `nLength`  
 Die Anzahl der Zeichen im `pch`.  
  
 `pStringMgr`  
 Ein Zeiger auf Speicher-Manager, der die `CSimpleStringT` Objekt. Weitere Informationen zu `IAtlStringMgr` und Verwaltung des Arbeitsspeichers für `CSimpleStringT`, finden Sie unter [Speicherverwaltung und CStringT](../memory-management-with-cstringt.md).  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein neues `CSimpleStringT`-Objekt. Da die Konstruktoren die Eingabedaten in den neuen belegten Speicher kopieren, können Arbeitsspeicher Ausnahmen führen.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::CSimpleStringT` mithilfe der ATL `typedef` `CSimpleString`. `CSimpleString` häufig verwendete Spezialisierung eine Klassenvorlage ist `CSimpleStringT`.  
  
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

  
##  <a name="empty"></a>  CSimpleStringT::Empty
Macht diese `CSimpleStringT` Objekt eine leere Zeichenfolge und gibt Arbeitsspeicher nach Bedarf frei.  
  
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
  
##  <a name="freeextra"></a>  CSimpleStringT::FreeExtra
Zuvor durch die Zeichenfolge zugeordnet, jedoch nicht mehr benötigt zusätzlichen Speicher frei.  
  
### <a name="syntax"></a>Syntax  
  
```  
void FreeExtra(); 
```  
### <a name="remarks"></a>Hinweise  
 Dies sollte den Overhead der Arbeitsspeicher von der String-Objekt reduzieren. Die Methode ordnet den Puffer, die genaue Länge zurückgegebenes [GetLength](#getlength).  
  
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
 In diesem Beispiel wird die Ausgabe lautet wie folgt:  
  
 `Alloc length is 1031, String length is 1024`  
  
 `Alloc length is 1031, String length is 15`  
  
 `Alloc length is 15, String length is 15`  
  
##  <a name="getalloclength"></a>  CSimpleStringT::GetAllocLength  
Ruft die zugeordnete Länge einer `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
int GetAllocLength() const throw();  
```  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen, die für dieses Objekt zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Bestimmen der Anzahl von Zeichen, die für diese zugeordneten `CSimpleStringT` Objekt. Finden Sie unter [FreeExtra](#freeextra) für ein Beispiel für das Aufrufen dieser Funktion.  
  
##  <a name="getat"></a>  CSimpleStringT::GetAt  
Gibt ein Zeichen aus einem `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
XCHAR GetAt(int iChar) const;
```  
#### <a name="parameters"></a>Parameter  
 `iChar`  
 Nullbasierten Index des Zeichens in die `CSimpleStringT` Objekt. Die `iChar` Parameter muss größer als oder gleich 0 und kleiner als der Rückgabewert von [GetLength](#getlength). Andernfalls `GetAt` wird eine Ausnahme generiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `XCHAR` , das das Zeichen an der angegebenen Position in der Zeichenfolge enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Zurückgeben des ein Zeichens, die vom angegebenen `iChar`. Der überladene Feldindex (`[]`)-Operator ist ein zweckmäßiger Alias für `GetAt`. Das null-Abschlusszeichen ist ohne Auslösen einer Ausnahme mit adressierbar `GetAt`. Es wird jedoch nicht gezählt von `GetLength`, und der zurückgegebene Wert ist 0.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie `CSimpleStringT::GetAt`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(s.GetAt(2) == _T('c'));
```
  
##  <a name="getbuffer"></a>  CSimpleStringT::GetBuffer  
Gibt einen Zeiger auf den internen Zeichenpuffer für die `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
PXSTR GetBuffer(int nMinBufferLength); 
PXSTR GetBuffer();
```  
#### <a name="parameters"></a>Parameter  
 `nMinBufferLength`  
 Die minimale Anzahl von Zeichen, die der Zeichenpuffer aufnehmen kann. Dieser Wert beinhaltet keinen Platz für ein null-Abschlusszeichen.  
  
 Wenn `nMinBufferLength` ist größer als die Länge des aktuellen Puffers `GetBuffer` des aktuellen Puffers zerstört, ersetzt ihn durch einen Puffer von der angeforderten Größe und setzt den Verweiszähler des Objekts auf 0 (null) zurück. Wenn Sie zuvor aufgerufen haben [LockBuffer](#lockbuffer) für diesen Puffer, die Sie verlieren der Sperre des Puffers.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `PXSTR` Zeiger auf das Objekt (auf Null endende) Zeichenpuffer.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Zurückgeben der Inhalt des Puffers für die `CSimpleStringT` Objekt. Das zurückgegebene `PXSTR` ist keine Konstante und daher ermöglicht die direkte Änderung von `CSimpleStringT` Inhalt.  
  
 Bei Verwendung den zurückgegebene Zeiger `GetBuffer` um den Inhalt der Zeichenfolge zu ändern, rufen Sie [ReleaseBuffer](#releasebuffer) vor der Verwendung einer anderen `CSimpleStringT` Membermethoden.  
  
 Die Adresse zurückgegebenes `GetBuffer` möglicherweise aufgrund ungültiger nach dem Aufruf von `ReleaseBuffer` da zusätzliche `CSimpleStringT` Vorgänge können dazu führen, dass die `CSimpleStringT` Puffer neu reserviert werden. Der Puffer ist nicht zugewiesen werden, wenn Sie nicht die Länge der Ändern der `CSimpleStringT`.  
  
 Der Pufferspeicher wird automatisch freigegeben wird, wenn die `CSimpleStringT` -Objekt zerstört wird.  
  
 Wenn Sie nachverfolgen die Länge der Zeichenfolge selbst, sollten Sie nicht das abschließende Nullzeichen anhängen. Sie müssen jedoch die endgültige Zeichenfolgenlänge angeben, wenn Sie den Puffer mit freigeben `ReleaseBuffer`. Wenn Sie ein abschließendes Nullzeichen anfügen, sollten Sie-1 (Standardwert) für die Länge übergeben. `ReleaseBuffer` Klicken Sie dann bestimmt die Länge des Puffers.  
  
 Es ist nicht genügend Arbeitsspeicher zum Erfüllen der `GetBuffer` anfordern, löst diese Methode eine CMemoryException *.  
  
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
  
##  <a name="getbuffersetlength"></a>  CSimpleStringT::GetBufferSetLength  
Gibt einen Zeiger auf den internen Zeichenpuffer für die `CSimpleStringT` Objekt abschneiden oder seine Länge wächst, soweit erforderlich, um genau die Länge, die im angegebenen `nLength`.  
  
### <a name="syntax"></a>Syntax  
  
```  
PXSTR GetBufferSetLength(int nLength);
```  
#### <a name="parameters"></a>Parameter  
 `nLength`  
 Die genaue Größe der der `CSimpleStringT` der Zeichenpuffer in Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `PXSTR` Zeiger auf das Objekt (auf Null endende) Zeichenpuffer.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen einer angegebenen Länge des im internen Puffer der `CSimpleStringT` Objekt. Das zurückgegebene `PXSTR` Zeiger ist nicht `const` und somit ermöglicht die direkte Änderung von `CSimpleStringT` Inhalt.  
  
 Bei Verwendung den zurückgegebene Zeiger [GetBufferSetLength](#getbuffersetlength) aufrufen, um den Inhalt der Zeichenfolge zu ändern, `ReleaseBuffer` zum Aktualisieren des internen Zustands des `CsimpleStringT` vor der Verwendung einer anderen `CSimpleStringT` Methoden.  
  
 Die Adresse zurückgegebenes `GetBufferSetLength` möglicherweise aufgrund ungültiger nach dem Aufruf von `ReleaseBuffer` da zusätzliche `CSimpleStringT` Vorgänge können dazu führen, dass die `CSimpleStringT` Puffer neu reserviert werden. Der Puffer nicht neu zugewiesen, wenn Sie nicht die Länge der Ändern der `CSimpleStringT`.  
  
 Der Pufferspeicher wird automatisch freigegeben wird, wenn die `CSimpleStringT` -Objekt zerstört wird.  
  
 Wenn Sie nachverfolgen die Länge der Zeichenfolge selbst, nicht fügen Sie keine das abschließende Nullzeichen. Wenn Sie den Puffer mit freigeben, geben Sie die endgültige Zeichenfolgenlänge muss `ReleaseBuffer`. Wenn Sie ein abschließendes Nullzeichen anfügen beim Aufrufen von `ReleaseBuffer`, übergeben Sie – 1 (Standard) für die Länge, die `ReleaseBuffer`, und `ReleaseBuffer` führt eine `strlen` im Puffer, um seine Länge zu bestimmen.  
  
 Weitere Informationen zu verweiszählung finden Sie unter den folgenden Artikeln:  
  
- [Verwaltung der Objektlebensdauer durch Verweiszählung](http://msdn.microsoft.com/library/windows/desktop/ms687260) im Windows SDK. 
  
- [Implementieren die Verweiszählung](http://msdn.microsoft.com/library/windows/desktop/ms693431) im Windows SDK.
  
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
  
##  <a name="getlength"></a>  CSimpleStringT::GetLength  
Gibt die Anzahl der Zeichen in der `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
int GetLength() const throw();  
```  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen in der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Anzahl der Zeichen im Objekt zurück. Die Anzahl die umfasst keine null-Abschlusszeichen.  
  
 Für Mehrbyte-Zeichensätzen (MBCS), setzt `GetLength` zählt jedes 8-Bit-Zeichen; bedeutet, dass ein führendes und nachfolgendes Byte in einer Multibyte-Zeichen als zwei Bytes gezählt werden. Finden Sie unter [FreeExtra](#freeextra) für ein Beispiel für das Aufrufen dieser Funktion.  
  
##  <a name="getmanager"></a>  CSimpleStringT::GetManager  
Ruft ab, der Speicher-Manager, der die `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
IAtlStringMgr* GetManager() const throw();  
```  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf Speicher-Manager für die `CSimpleStringT` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen des Speichers-Manager verwendet werden, indem die `CSimpleStringT` Objekt. Weitere Informationen zu Speicher-Manager und Zeichenfolgenobjekten, finden Sie unter [Speicherverwaltung und CStringT](../memory-management-with-cstringt.md).  
  
##  <a name="getstring"></a>  CSimpleStringT::GetString
Ruft die Zeichenfolge ab.  
  
### <a name="syntax"></a>Syntax  
  
```  
PCXSTR GetString() const throw();
```  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die zugeordnete Zeichenfolge Abrufen der `CSimpleStringT` Objekt.  
  
> [!NOTE]
>  Das zurückgegebene `PCXSTR` Zeiger `const` und lässt keine direkte Änderung von `CSimpleStringT` Inhalt.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::GetString`.  
  
```cpp  
CSimpleString str(pMgr);
str += _T("Cup soccer is best!");
_tprintf_s(_T("%s"), str.GetString());
```
  
##  <a name="isempty"></a>  CSimpleStringT::IsEmpty  
Tests einer `CSimpleStringT` Objekt für die leere Bedingung.  
  
### <a name="syntax"></a>Syntax  
  
```  
bool IsEmpty() const throw();  
```  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn die `CSimpleStringT` Objekt hat die Länge 0 ist andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um zu bestimmen, ob das Objekt eine leere Zeichenfolge enthält.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::IsEmpty`.  
  
```cpp  
CSimpleString s(pMgr);
ASSERT(s.IsEmpty());
```
  
##  <a name="lockbuffer"></a>  CSimpleStringT::LockBuffer  
Deaktiviert die verweiszählung, und schützt die Zeichenfolge im Puffer.  
  
### <a name="syntax"></a>Syntax  
  
```  
PXSTR LockBuffer();
```  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CSimpleStringT` Objekt oder eine Null-terminierte Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Sperren des Puffers, der die `CSimpleStringT` Objekt. Durch Aufrufen von `LockBuffer`, Sie erstellen eine Kopie der Zeichenfolge durch-1 für den Verweiszähler dieser Planergruppe. Wenn die Verweisanzahl den Wert-1 ist, gilt die Zeichenfolge im Puffer "gesperrt" sein. Klicken Sie im gesperrten Zustand, wird die Zeichenfolge auf zwei Arten geschützt:  
  
-   Keine andere Zeichenfolge kann einen Verweis auf die Daten in der gesperrten Zeichenfolge abzurufen, auch wenn diese Zeichenfolge in der gesperrten Zeichenfolge zugeordnet ist.  
  
-   Die gesperrte Zeichenfolge wird nie eine andere Zeichenfolge verweisen, auch wenn die andere Zeichenfolge an die gesperrten Zeichenfolge kopiert wird.  
  
 Sperren Sie die Zeichenfolge im Puffer, stellen Sie sicher, dass die Zeichenfolge exklusiven im Puffer intakt bleibt.  
  
 Nachdem Sie abgeschlossen haben `LockBuffer`, rufen Sie [UnlockBuffer](#unlockbuffer) den Verweiszähler auf 1 zurückzusetzen.  
  
> [!NOTE]
>  Beim Aufrufen [GetBuffer](#getbuffer) auf einen gesperrten Puffer und Sie legen die `GetBuffer` Parameter `nMinBufferLength` größer als die Länge des aktuellen Puffers, verlieren Sie die Sperre des Puffers. Solch ein Aufruf zum `GetBuffer` des aktuellen Puffers zerstört, ersetzt ihn durch einen Puffer von der angeforderten Größe und setzt den Verweiszähler auf 0 (null) zurück.  
  
 Weitere Informationen zu verweiszählung finden Sie unter den folgenden Artikeln:  
  
- [Verwaltung der Objektlebensdauer durch Verweiszählung](http://msdn.microsoft.com/library/windows/desktop/ms687260) im Windows SDK  
  
- [Implementieren die Verweiszählung](http://msdn.microsoft.com/library/windows/desktop/ms693431) im Windows SDK  
  
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
  
##  <a name="operator_at"></a>  CSimpleStringT::operator\[\]  
Mit dieser Funktion wird für den Zugriff auf ein einzelnes Zeichen, die Arrays von Zeichen.  
  
### <a name="syntax"></a>Syntax  
  
```  
XCHAR operator[](int iChar) const;
```  
#### <a name="parameters"></a>Parameter  
 `iChar`  
 Nullbasierten Index eines Zeichens in der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Der überladene Feldindex (`[]`) Operator gibt ein einzelnes Zeichen, die von der nullbasierte Index im angegebenen `iChar`. Dieser Operator ist eine bequeme Ersatz für die [GetAt](#getat) Memberfunktion.  
  
> [!NOTE]
>  Können Sie den Index (`[]`)-Operator zum Abrufen des Werts eines Zeichens in einer `CSimpleStringT`, aber Sie können nicht zum Ändern des Werts eines Zeichens in einer `CSimpleStringT`.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von **CSimpleStringT::operator []**.  
  
```cpp  
CSimpleString s(_T("abc"), pMgr);
ASSERT(s[1] == _T('b'));
```
  
## <a name="operator_at"></a>  CSimpleStringT::operator \[\]
Mit dieser Funktion wird für den Zugriff auf ein einzelnes Zeichen, die Arrays von Zeichen.  
  
### <a name="syntax"></a>Syntax  
  
```   
XCHAR operator[](int iChar) const;
```  
  
### <a name="parameters"></a>Parameter  
 `iChar`  
 Nullbasierten Index eines Zeichens in der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Der überladene Feldindex (`[]`) Operator gibt ein einzelnes Zeichen, die von der nullbasierte Index im angegebenen `iChar`. Dieser Operator ist eine bequeme Ersatz für die [GetAt](#getat) Memberfunktion.  
  
> [!NOTE]
>  Können Sie den Index (`[]`)-Operator zum Abrufen des Werts eines Zeichens in einer `CSimpleStringT`, aber Sie können nicht zum Ändern des Werts eines Zeichens in einer `CSimpleStringT`.  
  
  
##  <a name="operator_add_eq"></a>  CSimpleStringT::operator +=  
Verknüpft eine neue Zeichenfolge oder das Zeichen am Ende einer vorhandenen Zeichenfolge an.  
  
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
 Ein Zeiger auf eine Null-terminierte Zeichenfolge.  
  
 `strSrc`  
 Ein Zeiger auf ein vorhandenes `CSimpleStringT` Objekt.  
  
 *ch*  
 Das Zeichen, das angefügt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Der Operator akzeptiert eine andere `CSimpleStringT` Objekt oder ein Zeichen. Beachten Sie, dass der Arbeitsspeicher Ausnahmen auftreten, wenn Sie diese Verkettungsoperator verwenden, da für Zeichen hinzugefügt, um diese neuer Speicher zugeordnet werden kann `CSimpleStringT` Objekt.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von **CSimpleStringT::operator +=**.  
  
```cpp  
CSimpleString str(_T("abc"), pMgr);
ASSERT(_tcscmp((str += _T("def")), _T("abcdef")) == 0);
```
  
##  <a name="operator_eq"></a>  CSimpleStringT::operator =  
Weist einen neuen Wert zu einem `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
CSimpleStringT& operator =(PCXSTR pszSrc); 
CSimpleStringT& operator =(const CSimpleStringT& strSrc);
```  
#### <a name="parameters"></a>Parameter  
 `pszSrc`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge.  
  
 `strSrc`  
 Ein Zeiger auf ein vorhandenes `CSimpleStringT` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Zielzeichenfolge (links) bereits vorhanden sind, die zum Speichern der neuen Daten groß genug ist, wird keine neue speicherbelegung ausgeführt. Beachten Sie, dass der Arbeitsspeicher Ausnahmen auftreten, jedes Mal, wenn Sie den Zuweisungsoperator da häufig neue Speicher, zum Speichern der resultierenden reserviert wird `CSimpleStringT` Objekt.  
  
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
  
##  <a name="operator_pcxstr"></a>  CSimpleStringT::operator PCXSTR  

 Greift direkt in gespeicherten Zeichen auf eine `CSimpleStringT` Objekt als Zeichenfolge im C-Format.  
  
### <a name="syntax"></a>Syntax  
  
```  
operator PCXSTR() const throw();
```  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeichenzeiger auf den String-Daten.  
  
### <a name="remarks"></a>Hinweise  
 Keine Zeichen kopiert werden; nur ein Zeiger zurückgegeben. Achten Sie darauf, dass mit diesem Operator. Wenn Sie ändern eine `CString` Objekt nach dem Sie die Zeichenzeiger erhalten haben, können Sie eine neuzuordnung von Arbeitsspeicher, der den Zeiger ungültig verursachen.  
  
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
  
##  <a name="pcxstr"></a>  CSimpleStringT::PCXSTR
Ein Zeiger auf eine Konstante Zeichenfolge.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef ChTraitsBase< BaseType >::PCXSTR PCXSTR;    
```  
##  <a name="preallocate"></a>  CSimpleStringT::Preallocate  
Ordnet eine bestimmte Menge von Bytes für den `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
void Preallocate( int nLength);
```  
#### <a name="parameters"></a>Parameter  
 `nLength`  
 Die genaue Größe der der `CSimpleStringT` der Zeichenpuffer in Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um eine bestimmte Puffergröße für zuzuordnen, die die `CSimpleStringT` Objekt.  
  
 `CSimpleStringT` generiert eine `STATUS_NO_MEMORY` -Ausnahme aus, wenn sie Speicherplatz für der Zeichenpuffer zugewiesen werden kann. Standardmäßig erfolgt die speicherbelegung durch WIN32-API-Funktionen `HeapAlloc` oder `HeapReAlloc`.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::Preallocate`.  
  
```cpp  
CSimpleString str(pMgr);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
str.Preallocate(100);
_tprintf_s(_T("Allocated length: %d\n"), str.GetAllocLength());
```
  
##  <a name="pxstr"></a>  CSimpleStringT::PXSTR  
Ein Zeiger auf eine Zeichenfolge.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef ChTraitsBase< BaseType >::PXSTR PXSTR;  
```  
##  <a name="releasebuffer"></a>  CSimpleStringT::ReleaseBuffer  
Gibt die Steuerung des Puffers, der vom zugeordneten frei [GetBuffer](#getbuffer).  
  
### <a name="syntax"></a>Syntax  
  
```  
void ReleaseBuffer(int nNewLength = -1);
```  
#### <a name="parameters"></a>Parameter  
 `nNewLength`  
 Die neue Länge der Zeichenfolge in Zeichen, d. h. ein null-Abschlusszeichen wird dabei nicht mitgezählt. Wenn die Zeichenfolge null-termininiert ist, der Standardwert-1 legt die `CSimpleStringT` Größe auf die aktuelle Länge der Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um zuordnen oder Freigeben des Puffers von der String-Objekt. Wenn Sie wissen, dass die Zeichenfolge im Puffer Null-terminiert ist, können Sie weglassen der `nNewLength` Argument. Wenn die Zeichenfolge nicht null ist, beendet, verwenden Sie `nNewLength` seine Länge angeben. Die Adresse zurückgegebenes [GetBuffer](#getbuffer) ungültig ist, nach dem Aufruf von `ReleaseBuffer` oder ein anderes `CSimpleStringT` Vorgang.  
  
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
  
##  <a name="releasebuffersetlength"></a>  CSimpleStringT::ReleaseBufferSetLength

Gibt die Steuerung des Puffers, der vom zugeordneten frei [GetBuffer](#getbuffer).  
  
### <a name="syntax"></a>Syntax  
  
```  
void ReleaseBufferSetLength(int nNewLength);
```  
#### <a name="parameters"></a>Parameter  
 `nNewLength`  
 Die Länge der Zeichenfolge freigegeben wird  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist funktional mit [ReleaseBuffer](#releasebuffer) mit dem Unterschied, dass eine gültige Länge für den String-Objekt übergeben werden muss.  
  
##  <a name="setat"></a>  CSimpleStringT::SetAt  
Legt ein einzelnes Zeichen aus einer `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
void SetAt(int iChar, XCHAR ch);
```  
#### <a name="parameters"></a>Parameter  
 `iChar`  
 Nullbasierten Index des Zeichens in die `CSimpleStringT` Objekt. Die `iChar` Parameter muss größer als oder gleich 0 und kleiner als der Rückgabewert von [GetLength](#getlength).  
  
 *ch*  
 Das neue Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um zu überschreiben, das Zeichen am `iChar`. Diese Methode wird die Zeichenfolge nicht vergrößert, wenn `iChar` überschreitet die Begrenzungen der vorhandene Zeichenfolge.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::SetAt`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
s.SetAt(1, _T('a'));
ASSERT(_tcscmp(s, _T("aacdef")) == 0);
``` 
  
##  <a name="setmanager"></a>  CSimpleStringT::SetManager  
Gibt an, der Speicher-Manager, der die `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
void SetManager(IAtlStringMgr* pStringMgr);
```  
#### <a name="parameters"></a>Parameter  
 `pStringMgr`  
 Ein Zeiger auf den neuen Speichermanager.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Angeben eines neuen Speichers-Manager verwendet werden, indem die `CSimpleStringT` Objekt. Weitere Informationen zu Speicher-Manager und Zeichenfolgenobjekten, finden Sie unter [Speicherverwaltung und CStringT](../memory-management-with-cstringt.md).  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::SetManager`.  
  
```cpp  
CSimpleString s(pMgr);
s.SetManager(pCustomMgr);
```
  
##  <a name="setstring"></a>  CSimpleStringT::SetString  
Legt die Zeichenfolge von einem `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
void SetString(PCXSTR pszSrc, int nLength); 
void SetString(PCXSTR pszSrc);
```  
#### <a name="parameters"></a>Parameter  
 `pszSrc`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge.  
  
 `nLength`  
 Die Anzahl der Zeichen im `pszSrc`.  
  
### <a name="remarks"></a>Hinweise  
 Kopieren einer Zeichenfolge in der `CSimpleStringT` Objekt. `SetString` überschreibt die älteren Zeichenfolgendaten in den Puffer.  
  
 Beide Versionen des `SetString` überprüfen, ob `pszSrc` ist ein null-Zeiger und auszulösen, wenn dies der Fall, ein **E_INVALIDARG** Fehler.  
  
 Die Version 1-Parameter des `SetString` erwartet `pszSrc` auf eine Null-terminierte Zeichenfolge verweisen.  
  
 Die beiden Parameter-Version des `SetString` auch erwartet `pszSrc` eine Null-terminierte Zeichenfolge sein. Er verwendet `nLength` als die Länge der Zeichenfolge, wenn ein null-Abschlusszeichen zuerst gefunden wird.  
  
 Die beiden Parameter-Version des `SetString` auch überprüft, ob `pszSrc` verweist auf einen Speicherort des aktuellen Puffers in `CSimpleStringT`. In diesem speziellen Fall `SetString` verwendet eine Funktion zum Kopieren von Arbeitsspeicher, die nicht die Zeichenfolgendaten überschrieben wird, wie er die Zeichenfolgendaten zurück in den Puffer kopiert.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::SetString`.  
  
```cpp  
CSimpleString s(_T("abcdef"), pMgr);
ASSERT(_tcscmp(s, _T("abcdef")) == 0);
s.SetString(_T("Soccer"), 6);
ASSERT(_tcscmp(s, _T("Soccer")) == 0);
```
  
##  <a name="stringlength"></a>  CSimpleStringT::StringLength  
Gibt die Anzahl der Zeichen in der angegebenen Zeichenfolge zurück.  
  
### <a name="syntax"></a>Syntax  
  
```  
ATL_NOINLINE static int StringLength(PCXSTR psz) throw();
```  
#### <a name="parameters"></a>Parameter  
 `psz`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen in `psz`; ein null-Abschlusszeichen wird dabei nicht mitgezählt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen der Anzahl von Zeichen in der Zeichenfolge verweist `psz`.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `CSimpleStringT::StringLength`.  
  
```cpp  
ASSERT(CSimpleString::StringLength(_T("soccer")) == 6);
``` 
  
##  <a name="truncate"></a>  CSimpleStringT::Truncate
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
>  Dies wirkt sich nicht auf die zugeordnete Länge des Puffers. Zum Vergrößern, oder verringern den aktuellen Puffer, finden Sie unter [FreeExtra](#freeextra) und [Preallocate](#preallocate).  
  
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
  
##  <a name="unlockbuffer"></a>  CSimpleStringT::UnlockBuffer
 Entsperrt den Puffer der `CSimpleStringT` Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
void UnlockBuffer() throw();
```  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um den Verweiszähler der Zeichenfolge auf 1 zurückgesetzt.  
  
 Die `CSimpleStringT` Destruktor ruft automatisch `UnlockBuffer` um sicherzustellen, dass der Puffer nicht gesperrt ist, wenn der Destruktor aufgerufen wird. Ein Beispiel dieser Methode finden Sie unter [LockBuffer](#lockbuffer).  
  
##  <a name="dtor"></a>  CSimpleStringT:: ~ CSimpleStringT
Zerstört ein `CSimpleStringT`-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
~CSimpleStringT() throw();
```  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zerstört die `CSimpleStringT` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)