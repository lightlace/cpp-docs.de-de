---
title: CComSafeArray-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSafeArray
- ATLSAFE/ATL::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::Add
- ATLSAFE/ATL::CComSafeArray::Attach
- ATLSAFE/ATL::CComSafeArray::CopyFrom
- ATLSAFE/ATL::CComSafeArray::CopyTo
- ATLSAFE/ATL::CComSafeArray::Create
- ATLSAFE/ATL::CComSafeArray::Destroy
- ATLSAFE/ATL::CComSafeArray::Detach
- ATLSAFE/ATL::CComSafeArray::GetAt
- ATLSAFE/ATL::CComSafeArray::GetCount
- ATLSAFE/ATL::CComSafeArray::GetDimensions
- ATLSAFE/ATL::CComSafeArray::GetLowerBound
- ATLSAFE/ATL::CComSafeArray::GetSafeArrayPtr
- ATLSAFE/ATL::CComSafeArray::GetType
- ATLSAFE/ATL::CComSafeArray::GetUpperBound
- ATLSAFE/ATL::CComSafeArray::IsSizable
- ATLSAFE/ATL::CComSafeArray::MultiDimGetAt
- ATLSAFE/ATL::CComSafeArray::MultiDimSetAt
- ATLSAFE/ATL::CComSafeArray::Resize
- ATLSAFE/ATL::CComSafeArray::SetAt
- ATLSAFE/ATL::CComSafeArray::m_psa
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28be6dffc2f991ad08c83c508af2c401d5eecc37
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959370"
---
# <a name="ccomsafearray-class"></a>CComSafeArray-Klasse
Diese Klasse ist ein Wrapper für die `SAFEARRAY` Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```  
  
#### <a name="parameters"></a>Parameter  
 *T*  
 Der Typ der im Array gespeicherten Daten.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSafeArray::CComSafeArray](#ccomsafearray)|Der Konstruktor.|  
|[CComSafeArray:: ~ "CComSafeArray"](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSafeArray](#add)|Fügt eine oder mehrere Elemente oder ein `SAFEARRAY` -Struktur hinzu eine `CComSafeArray`.|  
|[CComSafeArray::Attach](#attach)|Fügt eine `SAFEARRAY` -Struktur in eine `CComSafeArray` Objekt.|  
|[CComSafeArray::CopyFrom](#copyfrom)|Kopiert den Inhalt einer `SAFEARRAY` -Struktur in der `CComSafeArray` Objekt.|  
|[CComSafeArray::CopyTo](#copyto)|Erstellt eine Kopie des `CComSafeArray`-Objekts.|  
|[CComSafeArray::Create](#create)|Erstellt ein `CComSafeArray`-Objekt.|  
|[CComSafeArray::Destroy](#destroy)|Zerstört ein `CComSafeArray`-Objekt.|  
|[CComSafeArray:: Detach](#detach)|Trennt eine `SAFEARRAY` aus einem `CComSafeArray` Objekt.|  
|[CComSafeArray::GetAt](#getat)|Ruft ein einzelnes Element aus einem eindimensionalen Array ab.|  
|[CComSafeArray::GetCount](#getcount)|Gibt die Anzahl der Elemente des Arrays zurück.|  
|[CComSafeArray::GetDimensions](#getdimensions)|Gibt die Anzahl der Dimensionen des Arrays zurück.|  
|[CComSafeArray::GetLowerBound](#getlowerbound)|Gibt die untere Grenze für eine bestimmte Dimension des Arrays zurück.|  
|[CComSafeArray::GetSafeArrayPtr](#getsafearrayptr)|Gibt die Adresse des `m_psa` -Datenelements zurück.|  
|[CComSafeArray::GetType](#gettype)|Gibt den Typ der im Array gespeicherten Daten zurück.|  
|[CComSafeArray::GetUpperBound](#getupperbound)|Gibt die obere Grenze für eine bestimmte Dimension des Arrays zurück.|  
|[CComSafeArray::IsSizable](#issizable)|Testet, ob die Größe eines `CComSafeArray` -Objekts geändert werden kann.|  
|[CComSafeArray::MultiDimGetAt](#multidimgetat)|Ruft ein einzelnes Element aus einem mehrdimensionalen Array ab.|  
|[CComSafeArray::MultiDimSetAt](#multidimsetat)|Legt den Wert eines Elements in einem mehrdimensionalen Array fest.|  
|[CComSafeArray::Resize](#resize)|Ändert die Größe eines `CComSafeArray` -Objekts.|  
|[CComSafeArray:: SetAt](#setat)|Legt den Wert eines Elements in einem eindimensionalen Array fest.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSafeArray::operator LPSAFEARRAY](#operator_lpsafearray)|Wandelt einen Wert in eine `SAFEARRAY` Zeiger.|  
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|Ruft ein Element aus dem Array ab.|  
|[CComSafeArray::operator =](#operator_eq)|Zuweisungsoperator.|  

  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSafeArray::m_psa](#m_psa)|Dieses Datenelement enthält die Adresse der `SAFEARRAY` Struktur.|  
  
## <a name="remarks"></a>Hinweise  
 `CComSafeArray` Stellt einen Wrapper für die [SAFEARRAY Data Type](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagsafearray) -Klasse, wodurch es problemlos erstellen und Verwalten von ein- und mehrdimensionale Arrays von nahezu jedem der VARIANT-unterstützten Typen.  
  
 `CComSafeArray` vereinfacht die Übergabe von Arrays zwischen Prozessen und bietet darüber hinaus zusätzliche Sicherheit durch Überprüfen der Arrayindexwerte anhand der oberen und unteren Grenzen.  
  
 Die untere Grenze eines `CComSafeArray` kann bei einem beliebigen benutzerdefinierten Wert beginnen, Arrays, auf die über C++ zugegriffen wird, sollte jedoch eine Untergrenze von 0 verwenden. Andere Sprachen wie Visual Basic können andere Begrenzungswerte (z. B. -10 bis 10) verwenden.  
  
 Verwenden Sie [CComSafeArray::Create](#create) , um ein `CComSafeArray` -Objekt zu erstellen, und [CComSafeArray::Destroy](#destroy) , um es zu löschen.  
  
 Ein `CComSafeArray` kann die folgende Teilmenge von VARIANT-Datentypen enthalten:  
  
|VARTYPE|Beschreibung|  
|-------------|-----------------|  
|VT_I1|char|  
|VT_I2|short|  
|VT_I4|int|  
|VT_I4|long|  
|VT_I8|longlong|  
|VT_UI1|byte|  
|VT_UI2|ushort|  
|VT_UI4|uint|  
|VT_UI4|ulong|  
|VT_UI8|ulonglong|  
|VT_R4|float|  
|VT_R8|double|  
|VT_DECIMAL|Dezimalzeiger|  
|VT_VARIANT|Variant-Zeiger|  
|VT_CY|Currency-Datentyp|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsafe.h  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]  
  
##  <a name="add"></a>  CComSafeArray  
 Fügt eine oder mehrere Elemente oder ein `SAFEARRAY` -Struktur hinzu eine `CComSafeArray`.  
  
```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *psaSrc*  
 Ein Zeiger auf eine `SAFEARRAY` Objekt.  
  
 *ulCount*  
 Die Anzahl von Objekten, in dem Array hinzugefügt werden soll.  
  
 *pT*  
 Ein Zeiger auf eine oder mehrere Objekte, die das Array hinzugefügt werden.  
  
 *t*  
 Ein Verweis auf das Objekt, das dem Array hinzugefügt werden.  
  
 *bCopy*  
 Gibt an, ob eine Kopie der Daten erstellt werden soll. Der Standardwert ist "true".  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die neuen Objekte werden an das Ende des vorhandenen angefügt `SAFEARRAY` Objekt. Hinzufügen eines Objekts auf ein mehrdimensionales `SAFEARRAY` Objekt wird nicht unterstützt. Wenn Sie ein vorhandenes Array von Objekten hinzufügen möchten, müssen beide Arrays Elemente desselben Typs enthalten.  
  
 Die *bCopy* Flag ist in Betracht gezogen, wenn Elemente des Typs BSTR oder Variante in ein Array hinzugefügt werden. Der Standardwert "true" wird sichergestellt, dass eine neue Kopie der Daten erstellt wird, wenn das Element des Arrays hinzugefügt wird.  
  
##  <a name="attach"></a>  CComSafeArray::Attach  
 Fügt eine `SAFEARRAY` -Struktur in eine `CComSafeArray` Objekt.  
  
```
HRESULT Attach(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>Parameter  
 *psaSrc*  
 Ein Zeiger auf die `SAFEARRAY` Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Fügt eine `SAFEARRAY` -Struktur in eine `CComSafeArray` -Objekts, indem die vorhandene `CComSafeArray` Methoden zur Verfügung.  
  
##  <a name="ccomsafearray"></a>  CComSafeArray::CComSafeArray  
 Der Konstruktor.  
  
```
CComSafeArray();
CComSafeArray(const SAFEARRAYBOUND& bound);
CComSafeArray(ULONG  ulCount, LONG lLBound = 0);
CComSafeArray(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
CComSafeArray(const CComSafeArray& saSrc);
CComSafeArray(const SAFEARRAY& saSrc);
CComSafeArray(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>Parameter  
 *Gebunden*  
 Eine `SAFEARRAYBOUND`-Struktur.  
  
 *ulCount*  
 Die Anzahl der Elemente im Array.  
  
 *lLBound*  
 Die unteren Grenzwert Das heißt, dass der Index des ersten Elements im Array.  
  
 *pBound*  
 Ein Zeiger auf eine `SAFEARRAYBOUND` Struktur.  
  
 *uDims*  
 Die Anzahl der Dimensionen im Array.  
  
 *saSrc*  
 Ein Verweis auf eine `SAFEARRAY` Struktur oder `CComSafeArray` Objekt. In beiden Fällen wird mit dem Konstruktor dieser Verweis erstellen Sie eine Kopie des Arrays aus, damit das Array nach der Erstellung nicht verwiesen wird.  
  
 *psaSrc*  
 Ein Zeiger auf eine `SAFEARRAY` Struktur. Der Konstruktor verwendet diese Adresse, erstellen Sie eine Kopie des Arrays aus, damit das Array nach der Erstellung nicht verwiesen wird.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein `CComSafeArray`-Objekt.  
  
##  <a name="dtor"></a>  CComSafeArray:: ~ "CComSafeArray"  
 Der Destruktor.  
  
```
~CComSafeArray() throw()
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="copyfrom"></a>  CComSafeArray::CopyFrom  
 Kopiert den Inhalt einer `SAFEARRAY` -Struktur in der `CComSafeArray` Objekt.  
  
```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>Parameter  
 *ppArray*  
 Zeiger auf die `SAFEARRAY` kopieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kopiert den Inhalt einer `SAFEARRAY` in das aktuelle `CComSafeArray` Objekt. Den vorhandenen Inhalt des Arrays werden ersetzt.  
  
##  <a name="copyto"></a>  CComSafeArray::CopyTo  
 Erstellt eine Kopie des `CComSafeArray`-Objekts.  
  
```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>Parameter  
 *ppArray*  
 Ein Zeiger auf einen Speicherort zum Erstellen des neuen `SAFEARRAY`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kopiert den Inhalt einer `CComSafeArray` -Objekt in ein `SAFEARRAY` Struktur.  
  
##  <a name="create"></a>  CComSafeArray::Create  
 Erstellt eine `CComSafeArray`.  
  
```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *pBound*  
 Ein Zeiger auf eine `SAFEARRAYBOUND` Objekt.  
  
 *uDims*  
 Die Anzahl der Dimensionen im Array.  
  
 *ulCount*  
 Die Anzahl der Elemente im Array.  
  
 *lLBound*  
 Die unteren Grenzwert Das heißt, dass der Index des ersten Elements im Array.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CComSafeArray` Objekt kann erstellt werden, aus einer vorhandenen `SAFEARRAYBOUND` Struktur und die Anzahl der Dimensionen, oder legen die Anzahl von Elementen in Arrays und die untere Grenze. Wenn das Array ist im Visual C++ zugegriffen werden, sollte die untere Grenze 0 sein. Andere Sprachen können andere Werte für die untere Grenze (z. B. Visual Basic unterstützt Arrays mit Elementen mit einem Bereich, z. B.-10 bis 10).  
  
##  <a name="destroy"></a>  CComSafeArray::Destroy  
 Zerstört ein `CComSafeArray`-Objekt.  
  
```
HRESULT Destroy();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Löscht eine vorhandene `CComSafeArray` Objekt und alle darin enthaltenen Daten.  
  
##  <a name="detach"></a>  CComSafeArray:: Detach  
 Trennt eine `SAFEARRAY` aus einem `CComSafeArray` Objekt.  
  
```
LPSAFEARRAY Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf eine `SAFEARRAY` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Trennt diese Methode die `SAFEARRAY` -Objekt aus der `CComSafeArray` Objekt.  
  
##  <a name="getat"></a>  CComSafeArray::GetAt  
 Ruft ein einzelnes Element aus einem eindimensionalen Array ab.  
  
```
T& GetAt(LONG lIndex) const;
```  
  
### <a name="parameters"></a>Parameter  
 *lIndex*  
 Die Indexnummer des Werts im zurückzugebenden Arrays.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf das erforderliche Arrayelement.  
  
##  <a name="getcount"></a>  CComSafeArray::GetCount  
 Gibt die Anzahl der Elemente des Arrays zurück.  
  
```
ULONG GetCount(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Parameter  
 *uDim*  
 Die Dimension des Arrays.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Elemente des Arrays zurück.  
  
### <a name="remarks"></a>Hinweise  
 Bei Verwendung mit einem mehrdimensionalen Array gibt diese Methode die Anzahl der Elemente in nur einer bestimmten Dimension zurück.  
  
##  <a name="getdimensions"></a>  CComSafeArray::GetDimensions  
 Gibt die Anzahl der Dimensionen des Arrays zurück.  
  
```
UINT GetDimensions() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Dimensionen des Arrays zurück.  
  
##  <a name="getlowerbound"></a>  CComSafeArray::GetLowerBound  
 Gibt die untere Grenze für eine bestimmte Dimension des Arrays zurück.  
  
```
LONG GetLowerBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Parameter  
 *uDim*  
 Die Arraydimension, für das die untere Grenze abgerufen werden soll. Wenn nicht angegeben, lautet der Standardwert 0.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die untere Grenze zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die untere Grenze 0 ist, bedeutet dies ein C-ähnlichen-Array, deren erstes Element Element Zahl 0 ist. Im Falle eines Fehlers, z. B. ungültige dimensionseinstellung Argument, diese Methode ruft `AtlThrow` mit dem HRESULT, der den Fehler beschreibt.  
  
##  <a name="getsafearrayptr"></a>  CComSafeArray::GetSafeArrayPtr  
 Gibt die Adresse des `m_psa` -Datenelements zurück.  
  
```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die [CComSafeArray::m_psa](#m_psa) -Datenmember.  
  
##  <a name="gettype"></a>  CComSafeArray::GetType  
 Gibt den Typ der im Array gespeicherten Daten zurück.  
  
```
VARTYPE GetType() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Typ der Daten in das Array, das einen der folgenden Typen handeln:  
  
|VARTYPE|Beschreibung|  
|-------------|-----------------|  
|VT_I1|char|  
|VT_I2|short|  
|VT_I4|int|  
|VT_I4|long|  
|VT_I8|longlong|  
|VT_UI1|byte|  
|VT_UI2|ushort|  
|VT_UI4|uint|  
|VT_UI4|ulong|  
|VT_UI8|ulonglong|  
|VT_R4|float|  
|VT_R8|double|  
|VT_DECIMAL|Dezimalzeiger|  
|VT_VARIANT|Variant-Zeiger|  
|VT_CY|Currency-Datentyp|  
  
##  <a name="getupperbound"></a>  CComSafeArray::GetUpperBound  
 Gibt die obere Grenze für eine bestimmte Dimension des Arrays zurück.  
  
```
LONG GetUpperBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Parameter  
 *uDim*  
 Die Arraydimension, für die die obere Grenze abgerufen werden soll. Wenn nicht angegeben, lautet der Standardwert 0.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die obere Grenze zurück. Dieser Wert ist, einschließlich der maximal gültigen Index für diese Dimension.  
  
### <a name="remarks"></a>Hinweise  
 Im Falle eines Fehlers, z. B. ungültige dimensionseinstellung Argument, diese Methode ruft `AtlThrow` mit dem HRESULT, der den Fehler beschreibt.  
  
##  <a name="issizable"></a>  CComSafeArray::IsSizable  
 Testet, ob die Größe eines `CComSafeArray` -Objekts geändert werden kann.  
  
```
bool IsSizable() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die `CComSafeArray` geändert werden kann, FALSE, wenn dies nicht möglich ist.  
  
##  <a name="m_psa"></a>  CComSafeArray::m_psa  
 Enthält die Adresse der `SAFEARRAY` Struktur zugreifen.  
  
```
LPSAFEARRAY m_psa;
```  
  
##  <a name="multidimgetat"></a>  CComSafeArray::MultiDimGetAt  
 Ruft ein einzelnes Element aus einem mehrdimensionalen Array ab.  
  
```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```  
  
### <a name="parameters"></a>Parameter  
 *alIndex*  
 Zeiger auf einen Vektor von Indizes für jede Dimension im Array. Ist der am weitesten links stehende (wichtigste) Dimension `alIndex[0]`.  
  
 *t*  
 Ein Verweis auf die zurückgegebenen Daten.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="multidimsetat"></a>  CComSafeArray::MultiDimSetAt  
 Legt den Wert eines Elements in einem mehrdimensionalen Array fest.  
  
```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```  
  
### <a name="parameters"></a>Parameter  
 *alIndex*  
 Zeiger auf einen Vektor von Indizes für jede Dimension im Array. Die Dimension des ganz rechts (am wenigsten signifikante) ist `alIndex`[0].  
  
 *T*  
 Gibt den Wert des neuen Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine mehrdimensionale Version der [CComSafeArray:: SetAt](#setat).  
  
##  <a name="operator_at"></a>  CComSafeArray::operator \[\]  
 Ruft ein Element aus dem Array ab.  
  
```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```  
  
### <a name="parameters"></a>Parameter  
 *lIndex, nIndex*  
 Die Indexnummer des gewünschten Elements im Array.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das entsprechende Array-Element.  
  
### <a name="remarks"></a>Hinweise  
 Führt eine ähnliche Funktion [CComSafeArray::GetAt](#getat), aber dieser Operator nur mit eindimensionalen Arrays funktioniert.  
  
##  <a name="operator_eq"></a>  CComSafeArray::operator =  
 Zuweisungsoperator.  
  
```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>Parameter  
 *saSrc*  
 Ein Verweis auf ein `CComSafeArray`-Objekt.  
  
 *psaSrc*  
 Ein Zeiger auf eine `SAFEARRAY` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Typ der im Array gespeicherten Daten zurück.  
  
##  <a name="operator_lpsafearray"></a>  CComSafeArray::operator LPSAFEARRAY  
 Wandelt einen Wert in eine `SAFEARRAY` Zeiger.  
  
```
operator LPSAFEARRAY() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wandelt einen Wert in eine `SAFEARRAY` Zeiger.  
  
##  <a name="resize"></a>  CComSafeArray::Resize  
 Ändert die Größe eines `CComSafeArray` -Objekts.  
  
```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *pBound*  
 Ein Zeiger auf eine `SAFEARRAYBOUND` -Struktur, die Informationen auf der Anzahl von Elementen und die untere Grenze eines Arrays enthält.  
  
 *ulCount*  
 Die angeforderte Anzahl der Objekte im Array dessen Größe geändert wurde.  
  
 *lLBound*  
 Die untere Grenze.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird nur die Dimension ganz rechts. Arrays, die zurückgegeben wird die Größe `IsResizable` als "false".  
  
##  <a name="setat"></a>  CComSafeArray:: SetAt  
 Legt den Wert eines Elements in einem eindimensionalen Array fest.  
  
```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *lIndex*  
 Die Indexnummer des Array-Elements festgelegt werden soll.  
  
 *t*  
 Der neue Wert des angegebenen Elements.  
  
 *bCopy*  
 Gibt an, ob eine Kopie der Daten erstellt werden soll. Der Standardwert ist "true".  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die *bCopy* Flag ist in Betracht gezogen, wenn Elemente des Typs BSTR oder Variante in ein Array hinzugefügt werden. Der Standardwert "true" wird sichergestellt, dass eine neue Kopie der Daten erstellt wird, wenn das Element des Arrays hinzugefügt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [SAFEARRAY-Datentyp](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagsafearray)   
 [CComSafeArray:: Create](#create)   
 [CComSafeArray:: Destroy](#destroy)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
