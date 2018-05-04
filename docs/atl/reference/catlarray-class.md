---
title: CAtlArray Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlArray
- ATLCOLL/ATL::CAtlArray
- ATLCOLL/ATL::Add
- ATLCOLL/ATL::Append
- ATLCOLL/ATL::AssertValid
- ATLCOLL/ATL::Copy
- ATLCOLL/ATL::FreeExtra
- ATLCOLL/ATL::GetAt
- ATLCOLL/ATL::GetCount
- ATLCOLL/ATL::GetData
- ATLCOLL/ATL::InsertArrayAt
- ATLCOLL/ATL::InsertAt
- ATLCOLL/ATL::IsEmpty
- ATLCOLL/ATL::RemoveAll
- ATLCOLL/ATL::RemoveAt
- ATLCOLL/ATL::SetAt
- ATLCOLL/ATL::SetAtGrow
- ATLCOLL/ATL::SetCount
- ATLCOLL/ATL::INARGTYPE
- ATLCOLL/ATL::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ceeaf5250cc9dc5cb4cb25c47b3fe179c7c5295
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="catlarray-class"></a>CAtlArray-Klasse
Diese Klasse implementiert ein Arrayobjekt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```  
  
#### <a name="parameters"></a>Parameter  
 *E*  
 Der Typ der im Array gespeicherten Daten.  
  
 *ETraits*  
 Der Code verwendet, um die Elemente kopiert oder verschoben.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Add](#add)|Rufen Sie diese Methode, um die Array-Objekt ein Element hinzuzufügen.|  
|[Anfügen](#append)|Rufen Sie diese Methode, um den Inhalt eines Arrays an das Ende einer anderen hinzufügen.|  
|["AssertValid"](#assertvalid)|Rufen Sie diese Methode, um sicherzustellen, dass das Arrayobjekt gültig ist.|  
|[CAtlArray](#catlarray)|Der Konstruktor.|  
|[~ CAtlArray](#dtor)|Der Destruktor.|  
|[Kopieren](#copy)|Rufen Sie diese Methode, um die Elemente eines Arrays auf einen anderen kopieren.|  
|[FreeExtra](#freeextra)|Rufen Sie diese Methode, um eine beliebige leere Elemente aus dem Array entfernt.|  
|[GetAt](#getat)|Rufen Sie diese Methode, um ein einzelnes Element aus dem Arrayobjekt abzurufen.|  
|[GetCount](#getcount)|Rufen Sie diese Methode, um die Anzahl der Elemente im Array gespeicherten zurück.|  
|[GetData](#getdata)|Rufen Sie diese Methode, um einen Zeiger auf das erste Element im Array zurückzugeben.|  
|[InsertArrayAt](#insertarrayat)|Rufen Sie diese Methode, um ein Array in eine andere einfügen.|  
|[InsertAt](#insertat)|Rufen Sie diese Methode zum Einfügen eines neuen Elements (oder mehrere Kopien eines Elements), in das Arrayobjekt.|  
|[IsEmpty](#isempty)|Rufen Sie diese Methode zu testen, ob das Array leer ist.|  
|[RemoveAll](#removeall)|Rufen Sie diese Methode, um alle Elemente aus dem Arrayobjekt zu entfernen.|  
|[RemoveAt](#removeat)|Rufen Sie diese Methode, um ein oder mehrere Elemente aus dem Array entfernt.|  
|[SetAt](#setat)|Rufen Sie diese Methode, um den Wert eines Elements in der Array-Objekt festlegen.|  
|[SetAtGrow](#setatgrow)|Rufen Sie diese Methode, um den Wert eines Elements im Arrayobjekt, das Array nach Bedarf erweitern festzulegen.|  
|[SetCount](#setcount)|Rufen Sie diese Methode, um die Größe des Array-Objekts festgelegt.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator&#91;&#93;](#operator_at)|Rufen Sie diesen Operator, um einen Verweis auf ein Element im Array zurückzugeben.|  

  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[INARGTYPE](#inargtype)|Der Datentyp zum Hinzufügen von Elementen auf das Array verwendet werden soll.|  
|[OUTARGTYPE](#outargtype)|Der Datentyp zum Abrufen von Elementen aus dem Array verwendet werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 **CAtlArray** stellt Methoden zum Erstellen und verwalten ein Array von Elementen eines benutzerdefinierten Typs. Obwohl die standard-C-Arrays ähnelt der **CAtlArray** Objekt dynamisch verkleinern und nach Bedarf wachsen kann. Der Arrayindex beginnt immer an Position 0, und die obere Grenze behoben oder erweitern, wenn neue Elemente hinzugefügt werden können.  
  
 Für Arrays mit einer kleinen Anzahl von Elementen, die ATL-Klasse [CSimpleArray](../../atl/reference/csimplearray-class.md) kann verwendet werden.  
  
 **CAtlArray** ist eng mit MFC verbunden **CArray** -Klasse und in einem MFC-Projekt, obwohl keine Serialisierungsunterstützung für die funktioniert.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="add"></a>  CAtlArray::Add  
 Rufen Sie diese Methode, um die Array-Objekt ein Element hinzuzufügen.  
  
```
size_t Add(INARGTYPE element);
size_t Add();
```  
  
### <a name="parameters"></a>Parameter  
 `element`  
 Das Element des Arrays hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Index des hinzugefügten Elements zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das neue Element wird bis zum Ende des Arrays hinzugefügt. Wenn kein Element angegeben wird, ein leeres Element hinzugefügt wird; das Array wird, also Größe erhöht, als wäre eine echte Element hinzugefügt wurde. Wenn der Vorgang fehlschlägt, ["atlthrow"](debugging-and-error-reporting-global-functions.md#atlthrow) mit dem Argument E_OUTOFMEMORY aufgerufen wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#1](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]  
  
##  <a name="append"></a>  CAtlArray::Append  
 Rufen Sie diese Methode, um den Inhalt eines Arrays an das Ende einer anderen hinzufügen.  
  
```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `aSrc`  
 Das Array, angefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Index des ersten Elements angefügt.  
  
### <a name="remarks"></a>Hinweise  
 Die Elemente im angegebenen Array werden bis zum Ende des vorhandenen Arrays hinzugefügt. Bei Bedarf wird Arbeitsspeicher zugeordnet werden, um die neuen Elemente aufzunehmen.  
  
 Die Arrays des gleichen Typs sein, und es ist nicht möglich, ein Array mit sich selbst angefügt werden soll.  
  
 Debug-Builds werden ein ATLASSERT ausgelöst, wenn die `CAtlArray` Argument ist ein gültiges Array oder, wenn `aSrc` bezieht sich auf das gleiche Objekt. Ungültige Argumente für die möglicherweise in Releasebuilds zu unvorhersehbarem Verhalten führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#2](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]  
  
##  <a name="assertvalid"></a>  CAtlArray::AssertValid  
 Rufen Sie diese Methode, um sicherzustellen, dass das Arrayobjekt gültig ist.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Arrayobjekt nicht gültig ist, ist `ATLASSERT` löst eine Assertion. Diese Methode ist nur verfügbar, wenn _DEBUG definiert ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#3](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]  
  
##  <a name="catlarray"></a>  CAtlArray::CAtlArray  
 Der Konstruktor.  
  
```
CAtlArray() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert das Arrayobjekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#4](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]  
  
##  <a name="dtor"></a>  CAtlArray:: ~ CAtlArray  
 Der Destruktor.  
  
```
~CAtlArray() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle vom Array-Objekt verwendeten Ressourcen frei.  
  
##  <a name="copy"></a>  CAtlArray::Copy  
 Rufen Sie diese Methode, um die Elemente eines Arrays auf einen anderen kopieren.  
  
```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `aSrc`  
 Die Quelle der Elemente in ein Array kopiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um Elemente einem Array mit den Elementen von einem anderen Array zu überschreiben. Bei Bedarf wird Arbeitsspeicher zugeordnet werden, um die neuen Elemente aufzunehmen. Es ist nicht möglich, Elemente eines Arrays mit sich selbst kopiert.  
  
 Wenn der vorhandene Inhalt des Arrays beibehalten werden sollen, verwenden [CAtlArray::Append](#append) stattdessen.  
  
 Debug-Builds werden ein ATLASSERT ausgelöst, wenn die vorhandene `CAtlArray` -Objekt ist ungültig, oder wenn `aSrc` bezieht sich auf das gleiche Objekt. Ungültige Argumente für die möglicherweise in Releasebuilds zu unvorhersehbarem Verhalten führen.  
  
> [!NOTE]
> `CAtlArray::Copy` unterstützt Arrays mit erstellten Elemente besteht nicht die [CAutoPtr](../../atl/reference/cautoptr-class.md) Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#5](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]  
  
##  <a name="freeextra"></a>  CAtlArray::FreeExtra  
 Rufen Sie diese Methode, um eine beliebige leere Elemente aus dem Array entfernt.  
  
```
void FreeExtra() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Leere Elemente entfernt werden, aber die Größe und die obere Grenze des Arrays, bleiben unverändert.  
  
 Debug-Builds wird ein ATLASSERT ausgelöst, wenn CAtlArray-Objekt ungültig ist oder wenn das Array die maximale Größe überschreiten würde.  
  
##  <a name="getat"></a>  CAtlArray::GetAt  
 Rufen Sie, dass diese Methode, um ein einzelnes Element aus dem Arrayobjekt abgerufen.  
  
```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `iElement`  
 Der Indexwert des Arrayelements zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf das Arrayelement erforderlich.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds werden ein ATLASSERT ausgelöst, wenn `iElement` überschreitet die Anzahl der Elemente im Array. In Releasebuilds möglicherweise ein ungültiges Argument zu unvorhersehbarem Verhalten führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#6](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]  
  
##  <a name="getcount"></a>  CAtlArray::GetCount  
 Rufen Sie diese Methode, um die Anzahl der Elemente im Array gespeicherten zurück.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Elemente im Array gespeicherten zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wie das erste Element im Array an Position 0 ist, wird der Wert zurückgegeben, indem `GetCount` ist immer 1 größer als der größte Index.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlArray::GetAt](#getat).  
  
##  <a name="getdata"></a>  CAtlArray::GetData  
 Rufen Sie diese Methode, um einen Zeiger auf das erste Element im Array zurückzugeben.  
  
```
E* GetData() throw();
const E* GetData() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die Speicheradresse, speichern das erste Element im Array an. Wenn keine Elemente verfügbar sind, wird NULL zurückgegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#7](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]  
  
##  <a name="inargtype"></a>  CAtlArray::INARGTYPE  
 Der Datentyp zum Hinzufügen von Elementen auf das Array verwendet werden soll.  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="insertarrayat"></a>  CAtlArray::InsertArrayAt  
 Rufen Sie diese Methode, um ein Array in eine andere einfügen.  
  
```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```  
  
### <a name="parameters"></a>Parameter  
 `iStart`  
 Der Index, an dem das Array eingefügt werden soll.  
  
 `paNew`  
 Das Array eingefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Elemente aus dem Array `paNew` in den Arrayobjekt, beginnend am Element kopiert werden `iStart`. Vorhandenen Arrayelemente werden verschoben, um zu vermeiden, überschrieben werden.  
  
 Debug-Builds werden ein ATLASSERT ausgelöst, wenn die `CAtlArray` -Objekt ist ungültig, oder wenn die `paNew` Zeiger ist NULL oder ungültig.  
  
> [!NOTE]
> `CAtlArray::InsertArrayAt` unterstützt Arrays mit erstellten Elemente besteht nicht die [CAutoPtr](../../atl/reference/cautoptr-class.md) Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#8](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]  
  
##  <a name="insertat"></a>  CAtlArray::InsertAt  
 Rufen Sie diese Methode zum Einfügen eines neuen Elements (oder mehrere Kopien eines Elements), in das Arrayobjekt.  
  
```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `iElement`  
 Der Index, in dem Elemente eingefügt werden.  
  
 `element`  
 Der Wert des Elements oder Elemente eingefügt werden.  
  
 `nCount`  
 Die Anzahl der hinzuzufügenden Elemente.  
  
### <a name="remarks"></a>Hinweise  
 Fügt eine oder mehrere Elemente in das Array, beginnend bei Index `iElement`. Vorhandene Elemente werden verschoben, um zu vermeiden, überschrieben werden.  
  
 Debug-Builds werden ein ATLASSERT ausgelöst, wenn die `CAtlArray` Objekt ist ungültig, die Anzahl der Elemente hinzugefügt werden, ist 0 (null) oder die kombinierte Anzahl von Elementen ist zu groß für das Array enthält. In Verkaufsversionen möglicherweise ungültige Parameter übergeben zu unvorhersehbaren Ergebnissen führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#9](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]  
  
##  <a name="isempty"></a>  CAtlArray::IsEmpty  
 Rufen Sie diese Methode zu testen, ob das Array leer ist.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn das Array leer ist, andernfalls false.  
  
### <a name="remarks"></a>Hinweise  
 Das Array gilt als leer, wenn es keine Elemente enthält. Auch wenn das Array leer Elemente enthält, ist es daher nicht leer.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#10](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]  
  
##  <a name="operator_at"></a>  CAtlArray::operator]  
 Rufen Sie diesen Operator, um einen Verweis auf ein Element im Array zurückzugeben.  
  
```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `iElement`  
 Der Indexwert des Arrayelements zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf das Arrayelement erforderlich.  
  
### <a name="remarks"></a>Hinweise  
 Führt eine ähnliche Funktion [CAtlArray::GetAt](#getat). Im Gegensatz zu den MFC-Klasse [CArray](../../mfc/reference/carray-class.md), dieser Operator kann nicht verwendet werden, als Ersatz für [CAtlArray::SetAt](#setat).  
  
 Debug-Builds werden ein ATLASSERT ausgelöst, wenn `iElement` überschreitet die Gesamtanzahl der Elemente im Array. In Verkaufsversionen kann ein ungültiger Parameter zu unvorhersehbaren Ergebnissen führen.  
  
##  <a name="outargtype"></a>  CAtlArray::OUTARGTYPE  
 Der Datentyp zum Abrufen von Elementen aus dem Array verwendet werden soll.  
  
```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```  
  
##  <a name="removeall"></a>  CAtlArray::RemoveAll  
 Rufen Sie diese Methode, um alle Elemente aus dem Arrayobjekt zu entfernen.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle Elemente aus dem Arrayobjekt.  
  
 Diese Methode ruft [CAtlArray::SetCount](#setcount) um die Größe des Arrays und gibt anschließend alle zugeordneten Arbeitsspeicher frei.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlArray::IsEmpty](#isempty).  
  
##  <a name="removeat"></a>  CAtlArray::RemoveAt  
 Rufen Sie diese Methode, um ein oder mehrere Elemente aus dem Array entfernt.  
  
```
void RemoveAt(size_t iElement, size_t nCount = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `iElement`  
 Der Index des ersten zu entfernenden Elements.  
  
 `nCount`  
 Die Anzahl der zu entfernenden Elemente.  
  
### <a name="remarks"></a>Hinweise  
 Entfernt eine oder mehrere Elemente aus dem Array. Alle verbleibenden Elemente werden nach unten verschoben. Die obere Grenze wird verringert, aber Speicher ist nicht reserviert, bis ein Aufruf von [CAtlArray::FreeExtra](#freeextra) erfolgt.  
  
 Debug-Builds werden ein ATLASSERT ausgelöst, wenn die `CAtlArray` -Objekt ist ungültig, oder wenn die kombinierte Summe `iElement` und `nCount` überschreitet die Gesamtanzahl der Elemente im Array. In Verkaufsversionen möglicherweise ungültige Parameter zu unvorhersehbaren Ergebnissen führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#11](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]  
  
##  <a name="setat"></a>  CAtlArray::SetAt  
 Rufen Sie diese Methode, um den Wert eines Elements in der Array-Objekt festlegen.  
  
```
void SetAt(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parameter  
 `iElement`  
 Der Index verweist auf das Arrayelement festlegen.  
  
 `element`  
 Der neue Wert des angegebenen Elements.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds werden ein ATLASSERT ausgelöst, wenn `iElement` überschreitet die Anzahl der Elemente im Array. In Verkaufsversionen kann ein ungültiger Parameter zu unvorhersehbaren Ergebnissen führen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlArray::GetAt](#getat).  
  
##  <a name="setcount"></a>  CAtlArray::SetCount  
 Rufen Sie diese Methode, um die Größe des Array-Objekts festgelegt.  
  
```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```  
  
### <a name="parameters"></a>Parameter  
 `nNewSize`  
 Die erforderliche Größe des Arrays.  
  
 `nGrowBy`  
 Ein Wert, der verwendet wird, um zu bestimmen, wie groß, um den Puffer zu machen. Der Wert-1 bewirkt, dass einen intern berechneten Wert verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn das Array erfolgreich Größe, andernfalls false ist.  
  
### <a name="remarks"></a>Hinweise  
 Das Array kann erhöht oder verringert die Größe sein. Wenn erhöht, werden zusätzliche leere Elemente des Arrays hinzugefügt. Wenn verringert wird, die Elemente mit der größten Indizes gelöscht werden, und Arbeitsspeicher freigegeben.  
  
 Verwenden Sie diese Methode, um die Größe des Arrays festgelegt wird, bevor Sie sie verwenden. Wenn `SetCount` nicht verwendet wird, der Vorgang des Hinzufügens von Elementen – und die nachfolgenden speicherbelegung ausgeführt, wird die Leistung verringern und des Arbeitsspeichers.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlArray::GetData](#getdata).  
  
##  <a name="setatgrow"></a>  CAtlArray::SetAtGrow  
 Rufen Sie diese Methode, um den Wert eines Elements im Arrayobjekt, das Array nach Bedarf erweitern festzulegen.  
  
```
void SetAtGrow(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parameter  
 `iElement`  
 Der Index verweist auf das Arrayelement festlegen.  
  
 `element`  
 Der neue Wert des angegebenen Elements.  
  
### <a name="remarks"></a>Hinweise  
 Ersetzt den Wert des Elements vom Index verweist. Wenn `iElement` ist größer als die aktuelle Größe des Arrays, das Array wird automatisch erhöht mithilfe eines Aufrufs [CAtlArray::SetCount](#setcount). Debug-Builds werden ein ATLASSERT ausgelöst, wenn die `CAtlArray` -Objekt ist ungültig. In Verkaufsversionen möglicherweise ungültige Parameter zu unvorhersehbaren Ergebnissen führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#12](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MMXSwarm-Beispiel](../../visual-cpp-samples.md)   
 [-Beispiel-Beispiel](../../visual-cpp-samples.md)   
 [UpdatePV-Beispiel](../../visual-cpp-samples.md)   
 [Laufschriften-Beispiel](../../visual-cpp-samples.md)   
 [CArray-Klasse](../../mfc/reference/carray-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
