---
title: COleSafeArray Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleSafeArray
- AFXDISP/COleSafeArray
- AFXDISP/COleSafeArray::COleSafeArray
- AFXDISP/COleSafeArray::AccessData
- AFXDISP/COleSafeArray::AllocData
- AFXDISP/COleSafeArray::AllocDescriptor
- AFXDISP/COleSafeArray::Attach
- AFXDISP/COleSafeArray::Clear
- AFXDISP/COleSafeArray::Copy
- AFXDISP/COleSafeArray::Create
- AFXDISP/COleSafeArray::CreateOneDim
- AFXDISP/COleSafeArray::Destroy
- AFXDISP/COleSafeArray::DestroyData
- AFXDISP/COleSafeArray::DestroyDescriptor
- AFXDISP/COleSafeArray::Detach
- AFXDISP/COleSafeArray::GetByteArray
- AFXDISP/COleSafeArray::GetDim
- AFXDISP/COleSafeArray::GetElement
- AFXDISP/COleSafeArray::GetElemSize
- AFXDISP/COleSafeArray::GetLBound
- AFXDISP/COleSafeArray::GetOneDimSize
- AFXDISP/COleSafeArray::GetUBound
- AFXDISP/COleSafeArray::Lock
- AFXDISP/COleSafeArray::PtrOfIndex
- AFXDISP/COleSafeArray::PutElement
- AFXDISP/COleSafeArray::Redim
- AFXDISP/COleSafeArray::ResizeOneDim
- AFXDISP/COleSafeArray::UnaccessData
- AFXDISP/COleSafeArray::Unlock
dev_langs:
- C++
helpviewer_keywords:
- COleSafeArray [MFC], COleSafeArray
- COleSafeArray [MFC], AccessData
- COleSafeArray [MFC], AllocData
- COleSafeArray [MFC], AllocDescriptor
- COleSafeArray [MFC], Attach
- COleSafeArray [MFC], Clear
- COleSafeArray [MFC], Copy
- COleSafeArray [MFC], Create
- COleSafeArray [MFC], CreateOneDim
- COleSafeArray [MFC], Destroy
- COleSafeArray [MFC], DestroyData
- COleSafeArray [MFC], DestroyDescriptor
- COleSafeArray [MFC], Detach
- COleSafeArray [MFC], GetByteArray
- COleSafeArray [MFC], GetDim
- COleSafeArray [MFC], GetElement
- COleSafeArray [MFC], GetElemSize
- COleSafeArray [MFC], GetLBound
- COleSafeArray [MFC], GetOneDimSize
- COleSafeArray [MFC], GetUBound
- COleSafeArray [MFC], Lock
- COleSafeArray [MFC], PtrOfIndex
- COleSafeArray [MFC], PutElement
- COleSafeArray [MFC], Redim
- COleSafeArray [MFC], ResizeOneDim
- COleSafeArray [MFC], UnaccessData
- COleSafeArray [MFC], Unlock
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 39c7a471b5c397c430f419514b9ebf1d4da62f62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="colesafearray-class"></a>COleSafeArray-Klasse
Eine Klasse zum Arbeiten mit Arrays beliebiger Dimension und beliebigen Typs.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleSafeArray : public tagVARIANT  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleSafeArray::COleSafeArray](#colesafearray)|Erstellt ein `COleSafeArray`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleSafeArray::AccessData](#accessdata)|Ruft einen Zeiger auf die Arraydaten.|  
|[COleSafeArray::AllocData](#allocdata)|Belegt Speicher für das Array an.|  
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|Belegt Speicher für den Deskriptor sicheres Array.|  
|[COleSafeArray::Attach](#attach)|Gibt Ihnen die Kontrolle der vorhandenen **VARIANT** array an die `COleSafeArray` Objekt.|  
|[COleSafeArray::Clear](#clear)|Gibt alle Daten in der zugrunde liegenden **VARIANT**.|  
|[COleSafeArray::Copy](#copy)|Erstellt eine Kopie eines vorhandenen Arrays.|  
|[COleSafeArray::Create](#create)|Erstellt ein sicheres Array.|  
|[COleSafeArray::CreateOneDim](#createonedim)|Erstellt ein eindimensionales `COleSafeArray` Objekt.|  
|[COleSafeArray::Destroy](#destroy)|Löscht ein vorhandenes Array.|  
|[COleSafeArray::DestroyData](#destroydata)|Daten in ein sicheres Array wird zerstört.|  
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|Zerstört einen Deskriptor eines sicheren Arrays an.|  
|[COleSafeArray::Detach](#detach)|Trennt die **VARIANT** array, aus der `COleSafeArray` Objekt (sodass die Daten werden nicht freigegeben).|  
|[COleSafeArray::GetByteArray](#getbytearray)|Kopiert den Inhalt der sicheren Arrays in einem [CByteArray](../../mfc/reference/cbytearray-class.md).|  
|[COleSafeArray::GetDim](#getdim)|Gibt die Anzahl der Dimensionen des Arrays zurück.|  
|[Colesafearray:: GetElement](#getelement)|Ruft ein einzelnes Element eines sicheren Arrays ab.|  
|[COleSafeArray::GetElemSize](#getelemsize)|Gibt die Größe in Bytes, der ein Element in ein sicheres Array zurück.|  
|[COleSafeArray::GetLBound](#getlbound)|Gibt die untere Grenze für eine Dimension eines sicheren Arrays zurück.|  
|[COleSafeArray::GetOneDimSize](#getonedimsize)|Gibt die Anzahl von Elementen im eindimensionalen `COleSafeArray` Objekt.|  
|[COleSafeArray::GetUBound](#getubound)|Gibt die obere Grenze für eine Dimension eines sicheren Arrays zurück.|  
|[COleSafeArray::Lock](#lock)|Inkrementiert die Sperrenanzahl eines Arrays, und einen Zeiger auf die Arraydaten im Arraydeskriptor platziert.|  
|[COleSafeArray::PtrOfIndex](#ptrofindex)|Gibt einen Zeiger auf das indizierte Element zurück.|  
|[COleSafeArray::PutElement](#putelement)|Weist ein einzelnes Element im Array zu.|  
|[COleSafeArray::Redim](#redim)|Ändert die wenigsten wichtigen Wert (ganz rechts) Grenze eines sicheren Arrays an.|  
|[COleSafeArray::ResizeOneDim](#resizeonedim)|Ändert die Anzahl der Elemente in einem eindimensionalen `COleSafeArray` Objekt.|  
|[COleSafeArray::UnaccessData](#unaccessdata)|Verringert die Sperre eines Arrays zu zählen und erklärt den Zeiger abgerufen, indem `AccessData`.|  
|[COleSafeArray::Unlock](#unlock)|Verringert die Sperrenanzahl eines Arrays, sodass es freigegeben oder dessen Größe geändert werden kann.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleSafeArray::operator LPCVARIANT](#operator_lpcvariant)|Greift auf die zugrunde liegende **VARIANT** Struktur der `COleSafeArray` Objekt.|  
|[COleSafeArray::operator LPVARIANT](#operator_lpvariant)|Greift auf die zugrunde liegende **VARIANT** Struktur der `COleSafeArray` Objekt.|  
|[COleSafeArray::operator =](#operator_eq)|Kopiert die Werte in einer `COleSafeArray` Objekt ( **SAFEARRAY**, **VARIANT**, `COleVariant`, oder `COleSafeArray` Arrays).|  
|[COleSafeArray::operator ==](#operator_eq_eq)|Vergleicht zwei Varianten Arrays ( **SAFEARRAY**, **Variante**, `COleVariant`, oder `COleSafeArray` Arrays).|  
|[COleSafeArray::operator&lt;&lt;](#operator_lt_lt)|Gibt den Inhalt von einem `COleSafeArray` Objekt in der Dumpkontext.|  
  
## <a name="remarks"></a>Hinweise  
 `COleSafeArray`leitet sich von der OLE **VARIANT** Struktur. Die OLE **SAFEARRAY** Memberfunktionen stehen über `COleSafeArray`, auch als Satz von Memberfunktionen, die speziell für eindimensionale Arrays von Bytes.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `tagVARIANT`  
  
 `COleSafeArray`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="accessdata"></a>COleSafeArray::AccessData  
 Ruft einen Zeiger auf die Arraydaten.  
  
```  
void AccessData(void** ppvData);
```  
  
### <a name="parameters"></a>Parameter  
 `ppvData`  
 Ein Zeiger auf einen Zeiger auf die Arraydaten.  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]  
  
##  <a name="allocdata"></a>COleSafeArray::AllocData  
 Belegt Speicher für ein sicheres Array.  
  
```  
void AllocData();
```  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="allocdescriptor"></a>COleSafeArray::AllocDescriptor  
 Belegt Speicher für den Deskriptor eines sicheren Arrays an.  
  
```  
void AllocDescriptor(DWORD dwDims);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDims`  
 Die Anzahl der Dimensionen in der sicheren Arrays.  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="attach"></a>COleSafeArray::Attach  
 Gibt Ihnen die Kontrolle der Daten in einer vorhandenen **VARIANT** array an die `COleSafeArray` Objekt.  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>Parameter  
 *varSrc*  
 Ein **VARIANT** Objekt. Die *VarSrc* Parameter benötigen die [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)**VT_ARRAY**.  
  
### <a name="remarks"></a>Hinweise  
 Die Quelle **VARIANT**Typ festgelegt ist, um `VT_EMPTY`. Diese Funktion löscht die aktuellen Daten des Arrays, sofern vorhanden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [COleSafeArray::AccessData](#accessdata).  
  
##  <a name="clear"></a>COleSafeArray::Clear  
 Löscht das sichere-Array.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion löscht ein sicheren Arrays durch Festlegen der `VARTYPE` des Objekts, das `VT_EMPTY`. Den aktuellen Inhalt freigegeben werden, und das Array wird freigegeben.  
  
##  <a name="colesafearray"></a>COleSafeArray::COleSafeArray  
 Erstellt ein `COleSafeArray`-Objekt.  
  
```  
COleSafeArray();

 
COleSafeArray(
    const SAFEARRAY& saSrc,
    VARTYPE vtSrc);

 
COleSafeArray(
    LPCSAFEARRAY pSrc,
    VARTYPE vtSrc);  
  
COleSafeArray(const COleSafeArray& saSrc);  
COleSafeArray(const VARIANT& varSrc);  
  COleSafeArray(LPCVARIANT pSrc);  
COleSafeArray(const COleVariant& varSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `saSrc`  
 Eine vorhandene `COleSafeArray` Objekt oder **SAFEARRAY** in das neue kopiert werden `COleSafeArray` Objekt.  
  
 `vtSrc`  
 Die **VARTYPE** des neuen `COleSafeArray` Objekt.  
  
 `psaSrc`  
 Ein Zeiger auf eine **SAFEARRAY** in das neue kopiert werden `COleSafeArray` Objekt.  
  
 *varSrc*  
 Eine vorhandene **VARIANT** oder `COleVariant` -Objekt, in das neue kopiert werden `COleSafeArray` Objekt.  
  
 `pSrc`  
 Ein Zeiger auf eine **VARIANT** -Objekt, in das neue kopiert werden `COleSafeArray` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Alle diese Konstruktoren erstellen Sie eine neue `COleSafeArray` Objekte. Wenn es keinen Parameter, ein leeres gibt `COleSafeArray` Objekt erstellt wird ( `VT_EMPTY`). Wenn die `COleSafeArray` wird kopiert, von einem anderen array, dessen [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) wird implizit bezeichnet (eine `COleSafeArray`, `COleVariant`, oder **VARIANT**), die **VARTYPE** von Das Quellarray beibehalten, und es muss nicht angegeben werden. Wenn die `COleSafeArray` wird kopiert, von einem anderen array, dessen **VARTYPE** nicht bekannt ist ( **SAFEARRAY**), die **VARTYPE** muss angegeben werden, der `vtSrc` Parameter.  
  
 Bei einem Fehler, löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="copy"></a>COleSafeArray::Copy  
 Erstellt eine Kopie eines vorhandenen sicheren Arrays.  
  
```  
void Copy(LPSAFEARRAY* ppsa);
```  
  
### <a name="parameters"></a>Parameter  
 *ppsa*  
 Zeiger auf einen Speicherort, in dem das neue Arraydeskriptor zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="create"></a>COleSafeArray::Create  
 Belegt, und die Daten für das Array initialisiert.  
  
```  
void Create(
    VARTYPE vtSrc,  
    DWORD dwDims,  
    DWORD* rgElements);

 
void Create(
    VARTYPE vtSrc,  
    DWORD dwDims,  
    SAFEARRAYBOUND* rgsabounds);
```  
  
### <a name="parameters"></a>Parameter  
 `vtSrc`  
 Der Basistyp des Arrays (d. h. die **VARTYPE** jedes Element des Arrays). Die **VARTYPE** auf eine Teilmenge von Varianten-Typen beschränkt ist. Weder die **VT_ARRAY** noch die **VT_BYREF** Flag festgelegt werden. `VT_EMPTY`und **VT_NULL** sind keine gültigen Basis-Typen für das Array. Alle anderen Typen sind zulässig.  
  
 `dwDims`  
 Die Anzahl der Dimensionen im Array. Dies kann geändert werden, nachdem das Array erstellt wurde, mit [Redim](#redim).  
  
 *rgElements*  
 Ein Zeiger auf ein Array von der Anzahl der Elemente für jede Dimension im Array.  
  
 *rgsabounds*  
 Zeiger auf einen Vektor von Grenzen (eine für jede Dimension) für das Array zuweisen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird die aktuelle Arraydaten bei Bedarf gelöscht werden. Bei einem Fehler, löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="createonedim"></a>COleSafeArray::CreateOneDim  
 Erstellt ein neues eindimensionales `COleSafeArray` Objekt.  
  
```  
void CreateOneDim(
    VARTYPE vtSrc,  
    DWORD dwElements,  
    const void* pvSrcData = NULL,  
    long nLBound = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `vtSrc`  
 Der Basistyp des Arrays (d. h. die **VARTYPE** jedes Element des Arrays).  
  
 `dwElements`  
 Anzahl der Elemente im Array. Dies kann geändert werden, nachdem das Array erstellt wurde, mit [ResizeOneDim](#resizeonedim).  
  
 `pvSrcData`  
 Zeiger auf die Daten in das Array kopieren.  
  
 *nLBound*  
 Die untere Grenze des Arrays.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion zuordnet und initialisiert die Daten für das Array, das die angegebenen Daten kopieren, wenn der Zeiger `pvSrcData` nicht **NULL**.  
  
 Bei einem Fehler, löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]  
  
##  <a name="destroy"></a>COleSafeArray::Destroy  
 Löscht einen vorhandenen Arraydeskriptor und alle Daten im Array.  
  
```  
void Destroy();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Objekte im Array gespeichert sind, wird jedes Objekt freigegeben. Bei einem Fehler, löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="destroydata"></a>COleSafeArray::DestroyData  
 Alle Daten in ein sicheres Array wird zerstört.  
  
```  
void DestroyData();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Objekte im Array gespeichert sind, wird jedes Objekt freigegeben. Bei einem Fehler, löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="destroydescriptor"></a>COleSafeArray::DestroyDescriptor  
 Zerstört einen Deskriptor eines sicheren Arrays an.  
  
```  
void DestroyDescriptor();
```  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="detach"></a>COleSafeArray::Detach  
 Trennt die **VARIANT** Daten aus der `COleSafeArray` Objekt.  
  
```  
VARIANT Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die zugrunde liegende **VARIANT** Wert in der `COleSafeArray` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion trennt die Daten in ein sicheres Array durch Festlegen der [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) des Objekts, das `VT_EMPTY`. Es ist das Array frei durch Aufrufen der Windows-Funktion in der Verantwortung des Aufrufers [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835).  
  
 Bei einem Fehler, löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [COleSafeArray::PutElement](#putelement).  
  
##  <a name="getbytearray"></a>COleSafeArray::GetByteArray  
 Kopiert den Inhalt der sicheren Arrays in einem `CByteArray`.  
  
```  
void GetByteArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>Parameter  
 `bytes`  
 Ein Verweis auf eine [CByteArray](../../mfc/reference/cbytearray-class.md) Objekt.  
  
##  <a name="getdim"></a>COleSafeArray::GetDim  
 Gibt die Anzahl der Dimensionen in der `COleSafeArray` Objekt.  
  
```  
DWORD GetDim();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Dimensionen in der sicheren Arrays.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="getelement"></a>Colesafearray:: GetElement  
 Ruft ein einzelnes Element eines sicheren Arrays ab.  
  
```  
void GetElement(
    long* rgIndices,  
    void* pvData);
```  
  
### <a name="parameters"></a>Parameter  
 `rgIndices`  
 Zeiger auf ein Array von Indizes für jede Dimension des Arrays.  
  
 `pvData`  
 Ein Zeiger auf den Speicherort für das Element des Arrays.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft automatisch die Windows-Funktionen `SafeArrayLock` und `SafeArrayUnlock` vor und nach dem Abrufen des Elements. Wenn das Datenelement eine Zeichenfolge, Objekt oder Variante ist, kopiert die Funktion das Element in korrekter Weise ab. Der Parameter `pvData` sollte zeigen Sie auf einer großen ausreichend Puffer, um das Element enthalten.  
  
 Bei einem Fehler, löst die Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]  
  
##  <a name="getelemsize"></a>COleSafeArray::GetElemSize  
 Ruft die Größe eines Elements in einem `COleSafeArray` Objekt.  
  
```  
DWORD GetElemSize();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe in Bytes, der die Elemente eines sicheren Arrays.  
  
##  <a name="getlbound"></a>COleSafeArray::GetLBound  
 Gibt die untere Grenze für eine bestimmte Dimension des ein `COleSafeArray` Objekt.  
  
```  
void GetLBound(
    DWORD dwDim,  
    long* pLBound);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDim`  
 Die Arraydimension, für die die untere Grenze abgerufen werden soll.  
  
 *pLBound*  
 Ein Zeiger auf die Position, an die untere Grenze zurück.  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]  
  
##  <a name="getonedimsize"></a>COleSafeArray::GetOneDimSize  
 Gibt die Anzahl von Elementen im eindimensionalen `COleSafeArray` Objekt.  
  
```  
DWORD GetOneDimSize();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von Elementen im eindimensionalen Array sicher.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [COleSafeArray::CreateOneDim](#createonedim).  
  
##  <a name="getubound"></a>COleSafeArray::GetUBound  
 Gibt die obere Grenze für eine Dimension eines sicheren Arrays zurück.  
  
```  
void GetUBound(
    DWORD dwDim,  
    long* pUBound);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDim`  
 Die Arraydimension, für die die obere Grenze abgerufen werden soll.  
  
 *pUBound*  
 Ein Zeiger auf die Position, an die obere Grenze zurück.  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst die Funktion eine [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]  
  
##  <a name="lock"></a>COleSafeArray::Lock  
 Inkrementiert den Verweiszähler der Sperre von einem Array und den Ort ein Zeiger auf die Arraydaten im Arraydeskriptor.  
  
```  
void Lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst es eine [COleException](../../mfc/reference/coleexception-class.md).  
  
 Der Zeiger im Arraydeskriptor ist gültig, bis `Unlock` aufgerufen wird. Aufrufe von `Lock` können geschachtelt sein; eine gleiche Anzahl von Aufrufen an `Unlock` erforderlich sind.  
  
 Ein Array kann nicht gelöscht werden, während es gesperrt ist.  
  
##  <a name="operator_lpcvariant"></a>COleSafeArray::operator LPCVARIANT  
 Rufen Sie diese Typumwandlungsoperator, um Zugriff auf die zugrunde liegenden **VARIANT** Struktur für dieses `COleSafeArray` Objekt.  
  
```  
operator LPCVARIANT() const;  
```  
  
##  <a name="operator_lpvariant"></a>COleSafeArray::operator LPVARIANT  
 Rufen Sie diese Typumwandlungsoperator, um Zugriff auf die zugrunde liegenden **VARIANT** Struktur für dieses `COleSafeArray` Objekt.  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass das Ändern des Werts in der **VARIANT** zugegriffen wird, die von dieser Funktion zurückgegebenen Zeiger Struktur ändert sich den Wert dieses `COleSafeArray` Objekt.  
  
##  <a name="operator_eq"></a>COleSafeArray::operator =  
 Diese überladenen Zuweisungsoperatoren kopieren den Quellwert in diese `COleSafeArray` Objekt.  
  
```  
COleSafeArray& operator=(const COleSafeArray& saSrc);  
COleSafeArray& operator=(const VARIANT& varSrc);  
  COleSafeArray& operator=(LPCVARIANT pSrc);  
COleSafeArray& operator=(const COleVariant& varSrc);
```  
  
### <a name="remarks"></a>Hinweise  
 Eine kurze Beschreibung der einzelnen Operatoren lautet folgendermaßen:  
  
- **Operator = (** *SaSrc* **)** kopiert eine vorhandene `COleSafeArray` -Objekts in dieses Objekt.  
  
- **Operator = (** *VarSrc***)** kopiert eine vorhandene **VARIANT** oder `COleVariant` Array, in dieses Objekt.  
  
- **Operator = (** `pSrc` **)** Kopien der **VARIANT** Array-Objekt zugegriffen `pSrc` in dieses Objekt.  
  
##  <a name="operator_eq_eq"></a>COleSafeArray::operator ==  
 Dieser Operator vergleicht zwei Arrays ( **SAFEARRAY**, **VARIANT**, `COleVariant`, oder `COleSafeArray` Arrays) und gibt einen Wert ungleich NULL, wenn sie gleich; andernfalls 0 sind.  
  
```  
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;  
   
BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;  
   
BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;  ```  
  
### Remarks  
 Two arrays are equal if they have an equal number of dimensions, equal size in each dimension, and equal element values.  
  
##  <a name="operator_lt_lt"></a>  COleSafeArray::operator &lt;&lt;  
 The `COleSafeArray` insertion (<<) operator supports diagnostic dumping and storing of a `COleSafeArray` object to an archive.  
  
```  
Operator CDumpContext & AFXAPI << (CDumpContext & dc  
    COleSafeArray & SaSrc);
```  
  
##  <a name="ptrofindex"></a>  COleSafeArray::PtrOfIndex  
 Returns a pointer to the element specified by the index values.  
  
```  
"void" PtrOfIndex (Long * RgIndices,  
    Operator Void ** PpvData);
```  
  
### Parameters  
 `rgIndices`  
 An array of index values that identify an element of the array. All indexes for the element must be specified.  
  
 `ppvData`  
 On return, pointer to the element identified by the values in `rgIndices`.  
  
##  <a name="putelement"></a>  COleSafeArray::PutElement  
 Assigns a single element into the array.  
  
```  
"void" PutElement (Long * RgIndices,  
    Void * PvData);
```  
  
### Parameters  
 `rgIndices`  
 Pointer to an array of indexes for each dimension of the array.  
  
 `pvData`  
 Pointer to the data to assign to the array. **VT_DISPATCH**, **VT_UNKNOWN**, and `VT_BSTR` variant types are pointers and do not require another level of indirection.  
  
### Remarks  
 This function automatically calls the Windows functions [SafeArrayLock](https://msdn.microsoft.com/library/windows/desktop/ms221492.aspx) and [SafeArrayUnlock](https://msdn.microsoft.com/library/windows/desktop/ms221246.aspx) before and after assigning the element. If the data element is a string, object, or variant, the function copies it correctly, and if the existing element is a string, object, or variant, it is cleared correctly.  
  
 Note that you can have multiple locks on an array, so you can put elements into an array while the array is locked by other operations.  
  
 On error, the function throws a [CMemoryException](../../mfc/reference/cmemoryexception-class.md) or [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
 [!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]  
  
##  <a name="redim"></a>  COleSafeArray::Redim  
 Changes the least significant (rightmost) bound of a safe array.  
  
```  
"void" Redim (SAFEARRAYBOUND * PsaboundNew);
```  
  
### Parameters  
 *psaboundNew*  
 Pointer to a new safe array bound structure containing the new array bound. Only the least significant dimension of an array may be changed.  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="resizeonedim"></a>  COleSafeArray::ResizeOneDim  
 Changes the number of elements in a one-dimensional `COleSafeArray` object.  
  
```  
"void" ResizeOneDim (DWORD DwElements);
```  
  
### Parameters  
 `dwElements`  
 Number of elements in the one-dimensional safe array.  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
  See the example for [COleSafeArray::CreateOneDim](#createonedim).  
  
##  <a name="unaccessdata"></a>  COleSafeArray::UnaccessData  
 Decrements the lock count of an array and invalidates the pointer retrieved by `AccessData`.  
  
```  
"void" UnaccessData();
```  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
  See the example for [COleSafeArray::AccessData](#accessdata).  
  
##  <a name="unlock"></a>  COleSafeArray::Unlock  
 Decrements the lock count of an array so it can be freed or resized.  
  
```  
"void" Unlock();
```  
  
### Remarks  
 This function is called after access to the data in an array is finished. On error, it throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
## See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)
