---
title: CComSafeArray-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 6e1337bee7dc6ca6f64f59657379f7d8ae40f5f8
ms.lasthandoff: 04/04/2017

---
# <a name="ccomsafearray-class"></a>CComSafeArray-Klasse
Diese Klasse ist ein Wrapper für die **SAFEARRAY** -Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der im Array gespeicherten Daten.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSafeArray::CComSafeArray](#ccomsafearray)|Der Konstruktor.|  
|[CComSafeArray:: ~ CComSafeArray](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSafeArray::Add](#add)|Fügt dem **eine oder mehrere Elemente oder eine** SAFEARRAY `CComSafeArray`-Struktur hinzu.|  
|[CComSafeArray::Attach](#attach)|Hängt einem **-Objekt eine** SAFEARRAY `CComSafeArray` -Struktur an.|  
|[CComSafeArray::CopyFrom](#copyfrom)|Kopiert den Inhalt einer **SAFEARRAY** -Struktur in das `CComSafeArray` -Objekt.|  
|[CComSafeArray::CopyTo](#copyto)|Erstellt eine Kopie des `CComSafeArray`-Objekts.|  
|[CComSafeArray:: Create](#create)|Erstellt ein `CComSafeArray`-Objekt.|  
|[CComSafeArray:: Destroy](#destroy)|Zerstört ein `CComSafeArray`-Objekt.|  
|[CComSafeArray::Detach](#detach)|Trennt ein **SAFEARRAY** von einem `CComSafeArray` -Objekt.|  
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
|[CComSafeArray::SetAt](#setat)|Legt den Wert eines Elements in einem eindimensionalen Array fest.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSafeArray::operator LPSAFEARRAY](#operator_lpsafearray)|Wandelt einen Wert in einen **SAFEARRAY** -Zeiger um.|  
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|Ruft ein Element aus dem Array ab.|  
|[CComSafeArray::operator =](#operator_eq)|Zuweisungsoperator.|  

  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSafeArray::m_psa](#m_psa)|Dieses Datenelement enthält die Adresse der **SAFEARRAY** -Struktur.|  
  
## <a name="remarks"></a>Hinweise  
 `CComSafeArray`Stellt einen Wrapper für die [SAFEARRAY-Datentyp](http://msdn.microsoft.com/en-us/9ec8025b-4763-4526-ab45-390c5d8b3b1e) -Klasse, wodurch es problemlos erstellen und Verwalten von ein- und mehrdimensionale Arrays von nahezu jedem der VARIANT-unterstützten Typen.  
  
 `CComSafeArray` vereinfacht die Übergabe von Arrays zwischen Prozessen und bietet darüber hinaus zusätzliche Sicherheit durch Überprüfen der Arrayindexwerte anhand der oberen und unteren Grenzen.  
  
 Die untere Grenze eines `CComSafeArray` kann bei einem beliebigen benutzerdefinierten Wert beginnen, Arrays, auf die über C++ zugegriffen wird, sollte jedoch eine Untergrenze von 0 verwenden. Andere Sprachen wie Visual Basic können andere Begrenzungswerte (z. B. -10 bis 10) verwenden.  
  
 Verwendung [CComSafeArray:: Create](#create) zum Erstellen einer `CComSafeArray` -Objekt, und [CComSafeArray:: Destroy](#destroy) zu löschen.  
  
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
 [!code-cpp[NVC_ATL_Utilities #75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]  
  
##  <a name="add"></a>CComSafeArray::Add  
 Fügt dem **eine oder mehrere Elemente oder eine** SAFEARRAY `CComSafeArray`-Struktur hinzu.  
  
```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `psaSrc`  
 Ein Zeiger auf eine **SAFEARRAY** Objekt.  
  
 `ulCount`  
 Die Anzahl von Objekten, die dem Array hinzugefügt werden soll.  
  
 *pT*  
 Ein Zeiger auf ein oder mehrere Objekte auf dem Array hinzugefügt werden.  
  
 *t*  
 Ein Verweis auf das Objekt, das das Array hinzugefügt werden.  
  
 `bCopy`  
 Gibt an, ob eine Kopie der Daten erstellt werden soll. Der Standardwert ist **"true"**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die neuen Objekte sind angefügt an das Ende des vorhandenen **SAFEARRAY** Objekt. Hinzufügen eines Objekts auf ein mehrdimensionales **SAFEARRAY** Objekt wird nicht unterstützt. Beim Hinzufügen eines vorhandenen Arrays von Objekten müssen beide Arrays Elemente des gleichen Typs enthalten.  
  
 Die `bCopy` Flag berücksichtigt wird bei der Elemente des Typs `BSTR` oder **VARIANT** ein Array hinzugefügt werden. Der Standardwert von **"true"** wird sichergestellt, dass eine neue Kopie der Daten erfolgt, wenn das Element des Arrays hinzugefügt wird.  
  
##  <a name="attach"></a>CComSafeArray::Attach  
 Hängt einem **-Objekt eine** SAFEARRAY `CComSafeArray` -Struktur an.  
  
```
HRESULT Attach(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `psaSrc`  
 Ein Zeiger auf die **SAFEARRAY** Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Fügt eine **SAFEARRAY** -Struktur in eine `CComSafeArray` Objekts, indem den vorhandenen `CComSafeArray` verfügbaren Methoden.  
  
##  <a name="ccomsafearray"></a>CComSafeArray::CComSafeArray  
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
 `bound`  
 Ein **SAFEARRAYBOUND** Struktur.  
  
 `ulCount`  
 Die Anzahl der Elemente im Array.  
  
 `lLBound`  
 Die untere Grenze Wert; d. h. den Index des ersten Elements im Array.  
  
 `pBound`  
 Ein Zeiger auf eine **SAFEARRAYBOUND** Struktur.  
  
 `uDims`  
 Die Anzahl der Dimensionen im Array.  
  
 `saSrc`  
 Ein Verweis auf eine **SAFEARRAY** Struktur oder `CComSafeArray` Objekt. In beiden Fällen wird mit dem Konstruktor dieser Verweis erstellen Sie eine Kopie des Arrays, damit das Array nach der Erstellung nicht verwiesen wird.  
  
 `psaSrc`  
 Ein Zeiger auf eine **SAFEARRAY** Struktur. Der Konstruktor verwendet diese Adresse in der eine Kopie des Arrays, sodass das Array nach der Erstellung nicht verwiesen wird.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein `CComSafeArray`-Objekt.  
  
##  <a name="dtor"></a>CComSafeArray:: ~ CComSafeArray  
 Der Destruktor.  
  
```
~CComSafeArray() throw()
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="copyfrom"></a>CComSafeArray::CopyFrom  
 Kopiert den Inhalt einer **SAFEARRAY** -Struktur in das `CComSafeArray` -Objekt.  
  
```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>Parameter  
 `ppArray`  
 Zeiger auf die **SAFEARRAY** zu kopieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kopiert den Inhalt einer **SAFEARRAY** in die aktuelle `CComSafeArray` Objekt. Ersetzt den vorhandenen Inhalt des Arrays.  
  
##  <a name="copyto"></a>CComSafeArray::CopyTo  
 Erstellt eine Kopie des `CComSafeArray`-Objekts.  
  
```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```  
  
### <a name="parameters"></a>Parameter  
 `ppArray`  
 Ein Zeiger auf einen Speicherort zum Erstellen des neuen **SAFEARRAY**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kopiert den Inhalt einer `CComSafeArray` -Objekt in ein **SAFEARRAY** Struktur.  
  
##  <a name="create"></a>CComSafeArray:: Create  
 Erstellt eine `CComSafeArray`.  
  
```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `pBound`  
 Ein Zeiger auf eine **SAFEARRAYBOUND** Objekt.  
  
 `uDims`  
 Die Anzahl der Dimensionen im Array.  
  
 `ulCount`  
 Die Anzahl der Elemente im Array.  
  
 `lLBound`  
 Die untere Grenze Wert; d. h. den Index des ersten Elements im Array.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CComSafeArray` Objekt kann erstellt werden, aus einer vorhandenen **SAFEARRAYBOUND** Struktur und die Anzahl der Dimensionen oder durch die Anzahl der Elemente im Array als auch die untere Grenze angeben. Wenn das Array ist Visual C++ zugreifen können, sollte die Untergrenze 0 sein. Andere Sprachen können andere Werte für die untere Grenze (z. B. Visual Basic unterstützt Arrays mit Elementen mit einem Bereich, z. B.-10 bis 10).  
  
##  <a name="destroy"></a>CComSafeArray:: Destroy  
 Zerstört ein `CComSafeArray`-Objekt.  
  
```
HRESULT Destroy();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Zerstört ein vorhandenes `CComSafeArray` Objekts und aller darin enthaltenen Daten.  
  
##  <a name="detach"></a>CComSafeArray::Detach  
 Trennt ein **SAFEARRAY** von einem `CComSafeArray` -Objekt.  
  
```
LPSAFEARRAY Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf eine **SAFEARRAY** Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löst die **SAFEARRAY** -Objekt aus der `CComSafeArray` Objekt.  
  
##  <a name="getat"></a>CComSafeArray::GetAt  
 Ruft ein einzelnes Element aus einem eindimensionalen Array ab.  
  
```
T& GetAt(LONG lIndex) const;
```  
  
### <a name="parameters"></a>Parameter  
 `lIndex`  
 Die Indexnummer des Werts im zurückzugebenden Arrays.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf das Arrayelement erforderlich.  
  
##  <a name="getcount"></a>CComSafeArray::GetCount  
 Gibt die Anzahl der Elemente des Arrays zurück.  
  
```
ULONG GetCount(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Parameter  
 `uDim`  
 Die Arraydimension.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Elemente des Arrays zurück.  
  
### <a name="remarks"></a>Hinweise  
 Bei Verwendung mit einem mehrdimensionalen Array gibt diese Methode die Anzahl der Elemente in einer bestimmten Dimension nur zurück.  
  
##  <a name="getdimensions"></a>CComSafeArray::GetDimensions  
 Gibt die Anzahl der Dimensionen des Arrays zurück.  
  
```
UINT GetDimensions() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Dimensionen des Arrays zurück.  
  
##  <a name="getlowerbound"></a>CComSafeArray::GetLowerBound  
 Gibt die untere Grenze für eine bestimmte Dimension des Arrays zurück.  
  
```
LONG GetLowerBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Parameter  
 `uDim`  
 Die Arraydimension, für die die untere Grenze abgerufen werden soll. Wenn nicht angegeben, lautet der Standardwert 0.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die untere Grenze zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Untergrenze 0 ist, bedeutet dies eine C-ähnliche-Array, dessen erste Element Element Zahl 0 ist. Im Falle eines Fehlers, z. B. eine ungültige Dimensionsargument diese Methode ruft `AtlThrow` mit dem HRESULT, der den Fehler beschreibt.  
  
##  <a name="getsafearrayptr"></a>CComSafeArray::GetSafeArrayPtr  
 Gibt die Adresse des `m_psa` -Datenelements zurück.  
  
```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die [CComSafeArray::m_psa](#m_psa) -Datenmember.  
  
##  <a name="gettype"></a>CComSafeArray::GetType  
 Gibt den Typ der im Array gespeicherten Daten zurück.  
  
```
VARTYPE GetType() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Typ der Daten in das Array, das eines der folgenden Typen handeln:  
  
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
  
##  <a name="getupperbound"></a>CComSafeArray::GetUpperBound  
 Gibt die obere Grenze für eine bestimmte Dimension des Arrays zurück.  
  
```
LONG GetUpperBound(UINT uDim = 0) const;
```  
  
### <a name="parameters"></a>Parameter  
 `uDim`  
 Die Arraydimension, für die die obere Grenze abgerufen werden soll. Wenn nicht angegeben, lautet der Standardwert 0.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die obere Grenze. Dieser Wert ist inklusiv, den maximal gültigen Index für diese Dimension.  
  
### <a name="remarks"></a>Hinweise  
 Im Falle eines Fehlers, z. B. eine ungültige Dimensionsargument diese Methode ruft `AtlThrow` mit dem HRESULT, der den Fehler beschreibt.  
  
##  <a name="issizable"></a>CComSafeArray::IsSizable  
 Testet, ob die Größe eines `CComSafeArray` -Objekts geändert werden kann.  
  
```
bool IsSizable() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn die `CComSafeArray` geändert werden kann, **"false"** Wenn dies nicht möglich.  
  
##  <a name="m_psa"></a>CComSafeArray::m_psa  
 Enthält die Adresse eines der **SAFEARRAY** Struktur zugegriffen.  
  
```
LPSAFEARRAY m_psa;
```  
  
##  <a name="multidimgetat"></a>CComSafeArray::MultiDimGetAt  
 Ruft ein einzelnes Element aus einem mehrdimensionalen Array ab.  
  
```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```  
  
### <a name="parameters"></a>Parameter  
 `alIndex`  
 Ein Zeiger auf einen Vektor von Indizes für jede Dimension im Array. Ist die am weitesten links stehende (wichtigste) Dimension `alIndex[0]`.  
  
 *t*  
 Ein Verweis auf die zurückgegebenen Daten.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="multidimsetat"></a>CComSafeArray::MultiDimSetAt  
 Legt den Wert eines Elements in einem mehrdimensionalen Array fest.  
  
```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```  
  
### <a name="parameters"></a>Parameter  
 `alIndex`  
 Ein Zeiger auf einen Vektor von Indizes für jede Dimension im Array. Die ganz rechts (am wenigsten signifikante) Dimension ist `alIndex`[0].  
  
 *T*  
 Gibt den Wert des neuen Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine mehrdimensionale Version des [CComSafeArray::SetAt](#setat).  
  
##  <a name="operator_at"></a>CComSafeArray::operator\[\]  
 Ruft ein Element aus dem Array ab.  
  
```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```  
  
### <a name="parameters"></a>Parameter  
 *lIndex nIndex*  
 Die Indexnummer des gewünschten Elements im Array.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das entsprechende Arrayelement zurück.  
  
### <a name="remarks"></a>Hinweise  
 Führt eine ähnliche Funktion [CComSafeArray::GetAt](#getat), aber dieser Operator nur mit eindimensionalen Arrays funktioniert.  
  
##  <a name="operator_eq"></a>CComSafeArray::operator =  
 Zuweisungsoperator.  
  
```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `saSrc`  
 Ein Verweis auf ein `CComSafeArray`-Objekt.  
  
 `psaSrc`  
 Ein Zeiger auf eine **SAFEARRAY** Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Typ der im Array gespeicherten Daten zurück.  
  
##  <a name="operator_lpsafearray"></a>CComSafeArray::operator LPSAFEARRAY  
 Wandelt einen Wert in einen **SAFEARRAY** -Zeiger um.  
  
```
operator LPSAFEARRAY() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wandelt einen Wert in einen **SAFEARRAY** -Zeiger um.  
  
##  <a name="resize"></a>CComSafeArray::Resize  
 Ändert die Größe eines `CComSafeArray` -Objekts.  
  
```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `pBound`  
 Ein Zeiger auf eine **SAFEARRAYBOUND** -Struktur, die Informationen für die Anzahl der Elemente und die Untergrenze eines Arrays enthält.  
  
 `ulCount`  
 Die angeforderte Anzahl von Objekten im Array dessen Größe geändert wurde.  
  
 `lLBound`  
 Die untere Grenze.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ändert nur die Dimension ganz rechts. Arrays, die zurückgegeben wird die Größe **IsResizable** als **"false"**.  
  
##  <a name="setat"></a>CComSafeArray::SetAt  
 Legt den Wert eines Elements in einem eindimensionalen Array fest.  
  
```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lIndex`  
 Die Indexnummer des Arrayelements festlegen.  
  
 *t*  
 Der neue Wert des angegebenen Elements.  
  
 `bCopy`  
 Gibt an, ob eine Kopie der Daten erstellt werden soll. Der Standardwert ist **"true"**.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die `bCopy` Flag berücksichtigt wird bei der Elemente des Typs `BSTR` oder **VARIANT** ein Array hinzugefügt werden. Der Standardwert von **"true"** wird sichergestellt, dass eine neue Kopie der Daten erfolgt, wenn das Element des Arrays hinzugefügt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [SAFEARRAY-Datentyp](http://msdn.microsoft.com/en-us/9ec8025b-4763-4526-ab45-390c5d8b3b1e)   
 [CComSafeArray:: Create](#create)   
 [CComSafeArray:: Destroy](#destroy)   
 [Klassenübersicht](../../atl/atl-class-overview.md)

