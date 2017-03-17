---
title: CAtlArray Class | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlArray
- ATLCOLL/ATL::CAtlArray
- ATLCOLL/ATL::Add
- ATLCOLL/ATL::Append
- ATLCOLL/ATL::AssertValid
- ATLCOLL/ATL::CAtlArray
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5fe987e428fc0dcf3e40bfb16aa26bcb90339aff
ms.lasthandoff: 02/24/2017

---
# <a name="catlarray-class"></a>CAtlArray-Klasse
Diese Klasse implementiert ein Array-Objekt.  
  
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
  
## <a name="members"></a>Mitglieder  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Add](#add)|Rufen Sie diese Methode, um das Array-Objekt ein Element hinzugefügt.|  
|[Anfügen](#append)|Rufen Sie diese Methode, um den Inhalt eines Arrays an das Ende eines anderen hinzufügen.|  
|["AssertValid"](#assertvalid)|Rufen Sie diese Methode, um zu bestätigen, dass das Array-Objekt gültig ist.|  
|[CAtlArray](#catlarray)|Der Konstruktor.|  
|[~ CAtlArray](#dtor)|Der Destruktor.|  
|[Kopieren](#copy)|Rufen Sie diese Methode, um die Elemente eines Arrays zu einem anderen zu kopieren.|  
|[FreeExtra](#freeextra)|Rufen Sie diese Methode, um leere Elemente aus dem Array entfernt.|  
|[GetAt](#getat)|Rufen Sie diese Methode, um ein einzelnes Element aus dem Arrayobjekt abzurufen.|  
|[GetCount](#getcount)|Rufen Sie diese Methode, um die Anzahl der Elemente im Array gespeicherten zurück.|  
|[GetData](#getdata)|Rufen Sie diese Methode, um einen Zeiger auf das erste Element im Array zurückgeben.|  
|[InsertArrayAt](#insertarrayat)|Rufen Sie diese Methode, um ein Array in ein anderes einzufügen.|  
|[InsertAt](#insertat)|Rufen Sie diese Methode zum Einfügen eines neuen Elements (oder mehrere Kopien eines Elements), in das Array-Objekt.|  
|[IsEmpty](#isempty)|Rufen Sie diese Methode, um festzustellen, ob das Array leer ist.|  
|[RemoveAll](#removeall)|Rufen Sie diese Methode, um alle Elemente aus dem Arrayobjekt zu entfernen.|  
|[RemoveAt](#removeat)|Rufen Sie diese Methode, um ein oder mehrere Elemente aus dem Array entfernt.|  
|[SetAt](#setat)|Rufen Sie diese Methode, um den Wert eines Elements in das Array-Objekt festlegen.|  
|[SetAtGrow](#setatgrow)|Rufen Sie diese Methode, um den Wert eines Elements in das Array-Objekt, das Array nach Bedarf erweitern festlegen.|  
|[SetCount](#setcount)|Rufen Sie diese Methode, um die Größe des Array-Objekts festgelegt.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator&#91;&#93;](#operator_at)|Rufen Sie diesen Operator, um einen Verweis auf ein Element im Array zurückgeben.|  

  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[INARGTYPE](#inargtype)|Der Datentyp für das Array Elemente hinzugefügt.|  
|[OUTARGTYPE](#outargtype)|Der Datentyp für das Abrufen von Elementen aus dem Array.|  
  
## <a name="remarks"></a>Hinweise  
 **CAtlArray** stellt Methoden zum Erstellen und verwalten ein Array von Elementen eines benutzerdefinierten Typs. Obwohl standard-C-Arrays, ähnelt der **CAtlArray** Objekt dynamisch verkleinern und nach Bedarf wachsen kann. Der Arrayindex beginnt immer an Position 0, und die obere Grenze festen oder erweitern neue Elemente hinzugefügt werden können.  
  
 Für Arrays mit einer kleinen Anzahl von Elementen, die ATL-Klasse [CSimpleArray](../../atl/reference/csimplearray-class.md) kann verwendet werden.  
  
 **CAtlArray** ist eng mit der MFC- **CArray** Klasse und funktioniert in einem MFC-Projekt auch ohne Unterstützung der Serialisierung.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="add"></a>CAtlArray::Add  
 Rufen Sie diese Methode, um das Array-Objekt ein Element hinzugefügt.  
  
```
size_t Add(INARGTYPE element);
size_t Add();
```  
  
### <a name="parameters"></a>Parameter  
 `element`  
 Das Element des Arrays hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Index des hinzugefügten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Das neue Element wird am Ende des Arrays hinzugefügt. Wenn kein Element bereitgestellt wird, wird ein leeres Element hinzugefügt wird; also ist das Array vergrößert, als ob eine echte Element hinzugefügt wurde. Wenn der Vorgang fehlschlägt, [AtlThrow](http://msdn.microsoft.com/library/2bd111da-8170-488d-914a-c9bf6b6765f7) wird mit dem Argument E_OUTOFMEMORY aufgerufen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#1;](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]  
  
##  <a name="append"></a>CAtlArray::Append  
 Rufen Sie diese Methode, um den Inhalt eines Arrays an das Ende eines anderen hinzufügen.  
  
```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `aSrc`  
 Das Array, angefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Index des ersten Elements angefügt.  
  
### <a name="remarks"></a>Hinweise  
 Das Ende des vorhandenen Arrays werden die Elemente im angegebenen Array hinzugefügt. Bei Bedarf wird Arbeitsspeicher zugeordnet werden, um die neuen Elemente aufnehmen zu können.  
  
 Die Arrays müssen vom selben Typ sein, und es ist nicht möglich, ein Array an sich selbst angefügt.  
  
 In Debugbuilds eine ATLASSERT wird ausgelöst, wenn die `CAtlArray` Argument ist ein gültiges Array oder `aSrc` bezieht sich auf das gleiche Objekt. Ungültige Argumente können in Releasebuilds zu unvorhersehbarem Verhalten führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#2;](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]  
  
##  <a name="assertvalid"></a>CAtlArray::AssertValid  
 Rufen Sie diese Methode, um zu bestätigen, dass das Array-Objekt gültig ist.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Array-Objekt nicht gültig ist, `ATLASSERT` löst eine Assertion. Diese Methode ist nur verfügbar, wenn _DEBUG definiert ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&3;](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]  
  
##  <a name="catlarray"></a>CAtlArray::CAtlArray  
 Der Konstruktor.  
  
```
CAtlArray() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert das Arrayobjekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&4;](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]  
  
##  <a name="dtor"></a>CAtlArray:: ~ CAtlArray  
 Der Destruktor.  
  
```
~CAtlArray() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle durch das Array-Objekt verwendeten Ressourcen werden freigegeben.  
  
##  <a name="copy"></a>CAtlArray::Copy  
 Rufen Sie diese Methode, um die Elemente eines Arrays zu einem anderen zu kopieren.  
  
```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `aSrc`  
 Die Quelle der Elemente, die in ein Array kopieren.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Elemente eines Arrays mit den Elementen eines anderen Arrays zu überschreiben. Bei Bedarf wird Arbeitsspeicher zugeordnet werden, um die neuen Elemente aufnehmen zu können. Es ist nicht möglich, Elemente eines Arrays auf sich selbst kopiert.  
  
 Wenn der vorhandene Inhalt des Arrays beibehalten werden sollen, verwenden [CAtlArray::Append](#append) stattdessen.  
  
 In Debugbuilds eine ATLASSERT wird ausgelöst, wenn die vorhandene `CAtlArray` -Objekt ist ungültig, oder wenn `aSrc` bezieht sich auf das gleiche Objekt. Ungültige Argumente können in Releasebuilds zu unvorhersehbarem Verhalten führen.  
  
> [!NOTE]
> `CAtlArray::Copy`unterstützt keine Arrays mit erstellte Elemente aus der [CAutoPtr](../../atl/reference/cautoptr-class.md) Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&5;](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]  
  
##  <a name="freeextra"></a>CAtlArray::FreeExtra  
 Rufen Sie diese Methode, um leere Elemente aus dem Array entfernt.  
  
```
void FreeExtra() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Leere Elemente werden entfernt, aber die Größe und die obere Grenze des Arrays bleiben unverändert.  
  
 Debug-Builds wird ein ATLASSERT ausgelöst, wenn CAtlArray-Objekt ungültig ist oder das Array seine maximale Größe überschreiten würde.  
  
##  <a name="getat"></a>CAtlArray::GetAt  
 Aufruf dieser Methode, um ein einzelnes Element aus dem Arrayobjekt abgerufen.  
  
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
 In Debugbuilds eine ATLASSERT wird ausgelöst, wenn `iElement` übersteigt die Anzahl der Elemente im Array. In Releasebuilds möglicherweise ein ungültiges Argument zu unvorhersehbarem Verhalten führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&6;](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]  
  
##  <a name="getcount"></a>CAtlArray::GetCount  
 Rufen Sie diese Methode, um die Anzahl der Elemente im Array gespeicherten zurück.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Elemente im Array gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Das erste Element im Array an Position 0 ist, wird der Wert von zurückgegeben `GetCount` ist immer 1 größer als der größte Index.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlArray::GetAt](#getat).  
  
##  <a name="getdata"></a>CAtlArray::GetData  
 Rufen Sie diese Methode, um einen Zeiger auf das erste Element im Array zurückgeben.  
  
```
E* GetData() throw();
const E* GetData() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die Speicheradresse, speichern das erste Element im Array an. Wenn keine Elemente verfügbar sind, wird NULL zurückgegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#7;](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]  
  
##  <a name="inargtype"></a>CAtlArray::INARGTYPE  
 Der Datentyp für das Array Elemente hinzugefügt.  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="insertarrayat"></a>CAtlArray::InsertArrayAt  
 Rufen Sie diese Methode, um ein Array in ein anderes einzufügen.  
  
```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```  
  
### <a name="parameters"></a>Parameter  
 `iStart`  
 Der Index, an dem das Array eingefügt werden.  
  
 `paNew`  
 Das Array eingefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Elemente aus dem Array `paNew` in den Arrayobjekt, beginnend am Element kopiert `iStart`. Vorhandenen Arrayelemente werden verschoben, um zu vermeiden, überschrieben werden.  
  
 In Debugbuilds eine ATLASSERT wird ausgelöst, wenn die `CAtlArray` -Objekt ist ungültig, oder wenn die `paNew` -Zeiger ist NULL oder ungültig.  
  
> [!NOTE]
> `CAtlArray::InsertArrayAt`unterstützt keine Arrays mit erstellte Elemente aus der [CAutoPtr](../../atl/reference/cautoptr-class.md) Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#8;](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]  
  
##  <a name="insertat"></a>CAtlArray::InsertAt  
 Rufen Sie diese Methode zum Einfügen eines neuen Elements (oder mehrere Kopien eines Elements), in das Array-Objekt.  
  
```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `iElement`  
 Der Index, in denen Elemente eingefügt werden.  
  
 `element`  
 Der Wert des Elements oder Elemente eingefügt werden.  
  
 `nCount`  
 Die Anzahl von Elementen hinzufügen.  
  
### <a name="remarks"></a>Hinweise  
 Fügt eine oder mehrere Elemente in das Array, beginnend am Index `iElement`. Vorhandene Elemente werden verschoben, zu vermeiden, überschrieben werden.  
  
 In Debugbuilds eine ATLASSERT wird ausgelöst, wenn die `CAtlArray` -Objekt ist ungültig, die Anzahl der hinzuzufügenden Elemente ist&0; (null) oder die kombinierte Anzahl der Elemente ist zu groß für das Array enthält. In Verkaufsversionen kann die Übergabe ungültiger Parameter zu unvorhersehbaren Ergebnissen führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#9;](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]  
  
##  <a name="isempty"></a>CAtlArray::IsEmpty  
 Rufen Sie diese Methode, um festzustellen, ob das Array leer ist.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn das Array leer ist, andernfalls false.  
  
### <a name="remarks"></a>Hinweise  
 Das Array wird als leer sein, wenn es keine Elemente enthält. Auch wenn das Array leere Elemente enthält, ist es daher nicht leer.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#10;](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]  
  
##  <a name="operator_at"></a>CAtlArray::operator]  
 Rufen Sie diesen Operator, um einen Verweis auf ein Element im Array zurückgeben.  
  
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
 Führt eine ähnliche Funktion [CAtlArray::GetAt](#getat). Im Gegensatz zu der MFC-Klasse [CArray](../../mfc/reference/carray-class.md), dieser Operator kann nicht verwendet werden, als Ersatz für [CAtlArray::SetAt](#setat).  
  
 In Debugbuilds eine ATLASSERT wird ausgelöst, wenn `iElement` überschreitet die Gesamtanzahl der Elemente im Array. Ein ungültiger Parameter kann zu unvorhersehbaren Ergebnissen führen, in Retail-Builds.  
  
##  <a name="outargtype"></a>CAtlArray::OUTARGTYPE  
 Der Datentyp für das Abrufen von Elementen aus dem Array.  
  
```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```  
  
##  <a name="removeall"></a>CAtlArray::RemoveAll  
 Rufen Sie diese Methode, um alle Elemente aus dem Arrayobjekt zu entfernen.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Entfernt alle Elemente aus dem Arrayobjekt.  
  
 Diese Methode ruft [CAtlArray::SetCount](#setcount) zum Ändern der Größe der Arrays und anschließend alle reservierten Speicher frei.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlArray::IsEmpty](#isempty).  
  
##  <a name="removeat"></a>CAtlArray::RemoveAt  
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
 Ein oder mehrere Elemente entfernt aus dem Array. Alle übrigen Elemente werden nach unten verschoben. Die obere Grenze wird verringert, aber Speicher wird nicht freigegeben, bis ein Aufruf [CAtlArray::FreeExtra](#freeextra) erfolgt.  
  
 In Debugbuilds eine ATLASSERT wird ausgelöst, wenn die `CAtlArray` -Objekt ist ungültig, oder wenn die kombinierte Summe `iElement` und `nCount` überschreitet die Gesamtanzahl der Elemente im Array. Ungültige Parameter können zu unvorhersehbaren Ergebnissen führen, in Retail-Builds.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#11;](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]  
  
##  <a name="setat"></a>CAtlArray::SetAt  
 Rufen Sie diese Methode, um den Wert eines Elements in das Array-Objekt festlegen.  
  
```
void SetAt(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parameter  
 `iElement`  
 Der Index verweist auf das Arrayelement festlegen.  
  
 `element`  
 Der neue Wert des angegebenen Elements.  
  
### <a name="remarks"></a>Hinweise  
 In Debugbuilds eine ATLASSERT wird ausgelöst, wenn `iElement` übersteigt die Anzahl der Elemente im Array. Ein ungültiger Parameter kann in Retail-Builds zu unvorhersehbaren Ergebnissen führen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlArray::GetAt](#getat).  
  
##  <a name="setcount"></a>CAtlArray::SetCount  
 Rufen Sie diese Methode, um die Größe des Array-Objekts festgelegt.  
  
```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```  
  
### <a name="parameters"></a>Parameter  
 `nNewSize`  
 Die erforderliche Größe des Arrays.  
  
 `nGrowBy`  
 Ein Wert, der bestimmt, wie groß den Puffer vornehmen. Der Wert-1 wird einen intern berechneten Wert verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn das Array erfolgreich Größe, andernfalls false ist.  
  
### <a name="remarks"></a>Hinweise  
 Das Array kann erhöht oder verringert die Größe sein. Wenn erhöht, werden zusätzliche leere Elemente des Arrays hinzugefügt. Verringert, die Elemente mit der größten Indizes werden gelöscht, und der Speicher freigegeben.  
  
 Verwenden Sie diese Methode, um die Größe des Arrays festgelegt wird, bevor Sie sie verwenden. Wenn `SetCount` nicht verwendet wird, Elemente hinzufügen – und die nachfolgenden speicherbelegung ausgeführt, wird die Leistung beeinträchtigt und des Arbeitsspeichers.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlArray::GetData](#getdata).  
  
##  <a name="setatgrow"></a>CAtlArray::SetAtGrow  
 Rufen Sie diese Methode, um den Wert eines Elements in das Array-Objekt, das Array nach Bedarf erweitern festlegen.  
  
```
void SetAtGrow(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parameter  
 `iElement`  
 Der Index verweist auf das Arrayelement festlegen.  
  
 `element`  
 Der neue Wert des angegebenen Elements.  
  
### <a name="remarks"></a>Hinweise  
 Ersetzt den Wert des Elements vom Index gezeigt wird. Wenn `iElement` ist größer als die aktuelle Größe des Arrays, das Array wird automatisch erhöht, mit einem Aufruf von [CAtlArray::SetCount](#setcount). In Debugbuilds eine ATLASSERT wird ausgelöst, wenn die `CAtlArray` -Objekt ist ungültig. Ungültige Parameter können zu unvorhersehbaren Ergebnissen führen, in Retail-Builds.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#12;](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MMXSwarm-Beispiel](../../visual-cpp-samples.md)   
 [DynamicConsumer-Beispiel](../../visual-cpp-samples.md)   
 [UpdatePV-Beispiel](../../visual-cpp-samples.md)   
 [Marquee-Beispiel](../../visual-cpp-samples.md)   
 [CArray-Klasse](../../mfc/reference/carray-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

