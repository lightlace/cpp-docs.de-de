---
title: Klasse COleSafeArray | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleSafeArray
dev_langs:
- C++
helpviewer_keywords:
- COleSafeArray class
- arrays [C++], safe
- safe arrays
- ODBC, safe arrays
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
caps.latest.revision: 22
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
ms.openlocfilehash: 3cb6fa49e3adf7e14c34baf7feb64d12e54f2758
ms.lasthandoff: 02/24/2017

---
# <a name="colesafearray-class"></a>COleSafeArray-Klasse
Eine Klasse zum Arbeiten mit Arrays beliebiger Dimension und beliebigen Typs.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleSafeArray : public tagVARIANT  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleSafeArray::COleSafeArray](#colesafearray)|Erstellt ein `COleSafeArray`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleSafeArray::AccessData](#accessdata)|Ruft einen Zeiger auf die Daten des Arrays ab.|  
|[COleSafeArray::AllocData](#allocdata)|Belegt Speicher für das Array.|  
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|Belegt Speicher für den Deskriptor sicheres Array.|  
|[COleSafeArray::Attach](#attach)|Steuerung des vorhandenen **VARIANT** array an die `COleSafeArray` Objekt.|  
|[COleSafeArray::Clear](#clear)|Entfernt alle Daten in der zugrunde liegenden **VARIANT**.|  
|[COleSafeArray::Copy](#copy)|Erstellt eine Kopie eines vorhandenen Arrays.|  
|[COleSafeArray::Create](#create)|Erstellt ein sicheres Array.|  
|[COleSafeArray::CreateOneDim](#createonedim)|Erstellt ein eindimensionales `COleSafeArray` Objekt.|  
|[COleSafeArray::Destroy](#destroy)|Löscht ein vorhandenes Array.|  
|[COleSafeArray::DestroyData](#destroydata)|Löscht die Daten in ein sicheres Array.|  
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|Zerstört einen Deskriptor eines sicheren Arrays.|  
|[COleSafeArray::Detach](#detach)|Trennt die **VARIANT** array, aus der `COleSafeArray` Objekt (, damit die Daten nicht freigegeben werden).|  
|[COleSafeArray::GetByteArray](#getbytearray)|Kopiert den Inhalt des sicheren Arrays in einem [CByteArray](../../mfc/reference/cbytearray-class.md).|  
|[COleSafeArray::GetDim](#getdim)|Gibt die Anzahl der Dimensionen des Arrays zurück.|  
|[COleSafeArray::GetElement](#getelement)|Ruft ein einzelnes Element eines sicheren Arrays ab.|  
|[COleSafeArray::GetElemSize](#getelemsize)|Gibt die Größe in Bytes, der ein Element in ein sicheres Array zurück.|  
|[COleSafeArray::GetLBound](#getlbound)|Gibt die untere Grenze für jede Dimension eines sicheren Arrays zurück.|  
|[COleSafeArray::GetOneDimSize](#getonedimsize)|Gibt die Anzahl von Elementen im eindimensionalen `COleSafeArray` Objekt.|  
|[COleSafeArray::GetUBound](#getubound)|Gibt die obere Grenze für jede Dimension eines sicheren Arrays zurück.|  
|[COleSafeArray::Lock](#lock)|Erhöht die Anzahl der Sperren eines Arrays und einen Zeiger auf die Daten des Arrays in den Arraydeskriptor.|  
|[COleSafeArray::PtrOfIndex](#ptrofindex)|Gibt einen Zeiger auf das indizierte Element zurück.|  
|[COleSafeArray::PutElement](#putelement)|Weist ein einzelnes Element im Array zu.|  
|[COleSafeArray::Redim](#redim)|Ändert die unwichtigste (ganz rechts) Grenze eines sicheren Arrays.|  
|[COleSafeArray::ResizeOneDim](#resizeonedim)|Ändert die Anzahl der Elemente in einem eindimensionalen `COleSafeArray` Objekt.|  
|[COleSafeArray::UnaccessData](#unaccessdata)|Verringert die Sperre eines Arrays zählen ungültig werden und den Zeiger abgerufen, indem `AccessData`.|  
|[COleSafeArray::Unlock](#unlock)|Verringert die Sperrenanzahl eines Arrays, sodass sie freigegeben oder angepasst werden kann.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleSafeArray::operator LPCVARIANT](#operator_lpcvariant)|Greift auf die zugrunde liegende **VARIANT** Struktur der `COleSafeArray` Objekt.|  
|[COleSafeArray::operator LPVARIANT](#operator_lpvariant)|Greift auf die zugrunde liegende **VARIANT** Struktur der `COleSafeArray` Objekt.|  
|[COleSafeArray::operator =](#operator_eq)|Kopiert die Werte in einer `COleSafeArray` Objekt ( **SAFEARRAY**, **VARIANT**, `COleVariant`, oder `COleSafeArray` Array).|  
|[COleSafeArray::operator ==](#operator_eq_eq)|Vergleicht zwei Varianten Arrays ( **SAFEARRAY**, **Variante**, `COleVariant`, oder `COleSafeArray` Arrays).|  
|[COleSafeArray::operator&lt;&lt;](#operator_lt_lt)|Gibt den Inhalt von einem `COleSafeArray` Objekt in der Dumpkontext.|  
  
## <a name="remarks"></a>Hinweise  
 `COleSafeArray`leitet sich von der OLE **VARIANT** Struktur. Die OLE **SAFEARRAY** Memberfunktionen stehen über `COleSafeArray`, auch als eine Reihe von Memberfunktionen, die speziell für eindimensionale Arrays von Bytes.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `tagVARIANT`  
  
 `COleSafeArray`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="a-nameaccessdataa--colesafearrayaccessdata"></a><a name="accessdata"></a>COleSafeArray::AccessData  
 Ruft einen Zeiger auf die Daten des Arrays ab.  
  
```  
void AccessData(void** ppvData);
```  
  
### <a name="parameters"></a>Parameter  
 `ppvData`  
 Ein Zeiger auf einen Zeiger auf die Daten des Arrays.  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst die Funktion einer [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException verfügt](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&#26;](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]  
  
##  <a name="a-nameallocdataa--colesafearrayallocdata"></a><a name="allocdata"></a>COleSafeArray::AllocData  
 Belegt Speicher für ein sicheres Array.  
  
```  
void AllocData();
```  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst die Funktion einer [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException verfügt](../../mfc/reference/coleexception-class.md).  
  
##  <a name="a-nameallocdescriptora--colesafearrayallocdescriptor"></a><a name="allocdescriptor"></a>COleSafeArray::AllocDescriptor  
 Belegt Speicher für den Deskriptor eines sicheren Arrays.  
  
```  
void AllocDescriptor(DWORD dwDims);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDims`  
 Die Anzahl der Dimensionen in dem SafeArray.  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst die Funktion einer [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException verfügt](../../mfc/reference/coleexception-class.md).  
  
##  <a name="a-nameattacha--colesafearrayattach"></a><a name="attach"></a>COleSafeArray::Attach  
 Steuerung der Daten in einer vorhandenen **VARIANT** array an die `COleSafeArray` Objekt.  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>Parameter  
 *varSrc*  
 Ein **VARIANT** Objekt. Die *VarSrc* Parameter müssen die [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)**VT_ARRAY**.  
  
### <a name="remarks"></a>Hinweise  
 Die Quelle **VARIANT**des festgelegt ist `VT_EMPTY`. Diese Funktion löscht die aktuellen Daten des Arrays, falls vorhanden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [COleSafeArray::AccessData](#accessdata).  
  
##  <a name="a-namecleara--colesafearrayclear"></a><a name="clear"></a>COleSafeArray::Clear  
 Löscht das SafeArray.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion löscht ein sicheres Array durch Festlegen der `VARTYPE` des Objekts, das `VT_EMPTY`. Der aktuelle Inhalt werden freigegeben, und das Array wird freigegeben.  
  
##  <a name="a-namecolesafearraya--colesafearraycolesafearray"></a><a name="colesafearray"></a>COleSafeArray::COleSafeArray  
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
 Eine vorhandene `COleSafeArray` Objekt oder **SAFEARRAY** in die neue kopiert werden `COleSafeArray` Objekt.  
  
 `vtSrc`  
 Die **VARTYPE** der neuen `COleSafeArray` Objekt.  
  
 `psaSrc`  
 Ein Zeiger auf eine **SAFEARRAY** in die neue kopiert werden `COleSafeArray` Objekt.  
  
 *varSrc*  
 Eine vorhandene **VARIANT** oder `COleVariant` -Objekt, in das neue kopiert werden `COleSafeArray` Objekt.  
  
 `pSrc`  
 Ein Zeiger auf eine **VARIANT** -Objekt, in das neue kopiert werden `COleSafeArray` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Alle diese Konstruktoren Erstellen neuer `COleSafeArray` Objekte. Wenn es keinen Parameter, ein leeres gibt `COleSafeArray` Objekt erstellt wird ( `VT_EMPTY`). Wenn die `COleSafeArray` stammt von einem anderen array, dessen [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) wird implizit bezeichnet (eine `COleSafeArray`, `COleVariant`, oder **VARIANT**), die **VARTYPE** des Quell-Array beibehalten wird, und muss nicht angegeben werden. Wenn die `COleSafeArray` stammt von einem anderen array, dessen **VARTYPE** ist nicht bekannt ( **SAFEARRAY**), die **VARTYPE** muss angegeben werden, der `vtSrc` Parameter.  
  
 Bei einem Fehler, löst die Funktion einer [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException verfügt](../../mfc/reference/coleexception-class.md).  
  
##  <a name="a-namecopya--colesafearraycopy"></a><a name="copy"></a>COleSafeArray::Copy  
 Erstellt eine Kopie eines vorhandenen Arrays sicher.  
  
```  
void Copy(LPSAFEARRAY* ppsa);
```  
  
### <a name="parameters"></a>Parameter  
 *ppsa*  
 Zeiger auf einen Speicherort in das neue Arraydeskriptor zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst die Funktion einer [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException verfügt](../../mfc/reference/coleexception-class.md).  
  
##  <a name="a-namecreatea--colesafearraycreate"></a><a name="create"></a>COleSafeArray::Create  
 Reserviert und die Daten für das Array initialisiert.  
  
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
 Der Basistyp des Arrays (d. h. die **VARTYPE** jedes Element des Arrays). Die **VARTYPE** auf eine Teilmenge der Varianten-Typen beschränkt ist. Weder der **VT_ARRAY** noch die **VT_BYREF** Flag festgelegt werden. `VT_EMPTY`und **VT_NULL** sind keine gültigen Basistypen für das Array. Alle anderen Typen sind zulässig.  
  
 `dwDims`  
 Die Anzahl der Dimensionen im Array. Dies kann geändert werden, nachdem das Array erstellt wurde, mit [Redim](#redim).  
  
 *rgElements*  
 Ein Zeiger auf ein Array von der Anzahl der Elemente für jede Dimension im Array.  
  
 *rgsabounds*  
 Zeiger auf einen Vektor von Grenzen (eine für jede Dimension) für das Array zugewiesen werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird die aktuelle Array-Daten bei Bedarf deaktivieren. Bei einem Fehler, löst die Funktion einer [CMemoryException](../../mfc/reference/cmemoryexception-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&#27;](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="a-namecreateonedima--colesafearraycreateonedim"></a><a name="createonedim"></a>COleSafeArray::CreateOneDim  
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
 Ein Zeiger auf die Daten in das Array kopiert.  
  
 *nLBound*  
 Die untere Grenze des Arrays.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion belegt und die Daten für die angegebenen Daten kopieren, wenn das Array initialisiert den Zeiger `pvSrcData` nicht **NULL**.  
  
 Bei einem Fehler, löst die Funktion einer [CMemoryException](../../mfc/reference/cmemoryexception-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&#28;](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]  
  
##  <a name="a-namedestroya--colesafearraydestroy"></a><a name="destroy"></a>COleSafeArray::Destroy  
 Löscht ein vorhandenes Arraydeskriptor und alle Daten im Array.  
  
```  
void Destroy();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Objekte im Array gespeichert werden, wird jedes Objekt freigegeben. Bei einem Fehler, löst die Funktion einer [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException verfügt](../../mfc/reference/coleexception-class.md).  
  
##  <a name="a-namedestroydataa--colesafearraydestroydata"></a><a name="destroydata"></a>COleSafeArray::DestroyData  
 Löscht alle Daten in ein sicheres Array.  
  
```  
void DestroyData();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Objekte im Array gespeichert werden, wird jedes Objekt freigegeben. Bei einem Fehler, löst die Funktion einer [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException verfügt](../../mfc/reference/coleexception-class.md).  
  
##  <a name="a-namedestroydescriptora--colesafearraydestroydescriptor"></a><a name="destroydescriptor"></a>COleSafeArray::DestroyDescriptor  
 Zerstört einen Deskriptor eines sicheren Arrays.  
  
```  
void DestroyDescriptor();
```  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst die Funktion einer [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException verfügt](../../mfc/reference/coleexception-class.md).  
  
##  <a name="a-namedetacha--colesafearraydetach"></a><a name="detach"></a>COleSafeArray::Detach  
 Trennt die **VARIANT** Daten aus der `COleSafeArray` Objekt.  
  
```  
VARIANT Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die zugrunde liegende **VARIANT** -Wert in der `COleSafeArray` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion trennt die Daten in ein sicheres Array durch Festlegen der [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) des Objekts, das `VT_EMPTY`. Es ist Aufgabe des Aufrufers Array freigeben, indem Sie die Windows-Funktion aufrufen [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835).  
  
 Bei einem Fehler, löst die Funktion einer [COleException verfügt](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [COleSafeArray::PutElement](#putelement).  
  
##  <a name="a-namegetbytearraya--colesafearraygetbytearray"></a><a name="getbytearray"></a>COleSafeArray::GetByteArray  
 Kopiert den Inhalt des sicheren Arrays in einem `CByteArray`.  
  
```  
void GetByteArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>Parameter  
 `bytes`  
 Ein Verweis auf eine [CByteArray](../../mfc/reference/cbytearray-class.md) Objekt.  
  
##  <a name="a-namegetdima--colesafearraygetdim"></a><a name="getdim"></a>COleSafeArray::GetDim  
 Gibt die Anzahl der Dimensionen in die `COleSafeArray` Objekt.  
  
```  
DWORD GetDim();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Dimensionen in dem SafeArray.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&#27;](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="a-namegetelementa--colesafearraygetelement"></a><a name="getelement"></a>COleSafeArray::GetElement  
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
 Diese Funktion ruft automatisch die Windows-Funktionen `SafeArrayLock` und `SafeArrayUnlock` vor und nach dem Abrufen des Elements. Wenn das Element eine Zeichenfolge, Objekt oder Variante ist, kopiert die Funktion das Element in korrekter Weise ab. Der Parameter `pvData` sollte auf eine große Puffer enthält das Element verweisen.  
  
 Bei einem Fehler, löst die Funktion einer [CMemoryException](../../mfc/reference/cmemoryexception-class.md) oder [COleException verfügt](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&#29;](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]  
  
##  <a name="a-namegetelemsizea--colesafearraygetelemsize"></a><a name="getelemsize"></a>COleSafeArray::GetElemSize  
 Ruft die Größe eines Elements in einem `COleSafeArray` Objekt.  
  
```  
DWORD GetElemSize();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe der Elemente eines sicheren Arrays in Bytes.  
  
##  <a name="a-namegetlbounda--colesafearraygetlbound"></a><a name="getlbound"></a>COleSafeArray::GetLBound  
 Gibt die untere Grenze für jede Dimension eine `COleSafeArray` Objekt.  
  
```  
void GetLBound(
    DWORD dwDim,  
    long* pLBound);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDim`  
 Die Dimension des Arrays, für die die untere Grenze abgerufen werden soll.  
  
 *pLBound*  
 Ein Zeiger auf den Speicherort für die untere Grenze zurück.  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst die Funktion einer [COleException verfügt](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&#30;](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]  
  
##  <a name="a-namegetonedimsizea--colesafearraygetonedimsize"></a><a name="getonedimsize"></a>COleSafeArray::GetOneDimSize  
 Gibt die Anzahl von Elementen im eindimensionalen `COleSafeArray` Objekt.  
  
```  
DWORD GetOneDimSize();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von Elementen im eindimensionalen Array sicher.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [COleSafeArray::CreateOneDim](#createonedim).  
  
##  <a name="a-namegetubounda--colesafearraygetubound"></a><a name="getubound"></a>COleSafeArray::GetUBound  
 Gibt die obere Grenze für jede Dimension eines sicheren Arrays zurück.  
  
```  
void GetUBound(
    DWORD dwDim,  
    long* pUBound);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDim`  
 Die Dimension des Arrays, für die die obere Grenze abgerufen werden soll.  
  
 *pUBound*  
 Zeiger auf die Position der oberen Grenze zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst die Funktion einer [COleException verfügt](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&#31;](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]  
  
##  <a name="a-namelocka--colesafearraylock"></a><a name="lock"></a>COleSafeArray::Lock  
 Erhöht die Anzahl der Sperren ein Array und den Ort ein Zeiger auf die Daten im Arraydeskriptor des Arrays.  
  
```  
void Lock();
```  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Fehler, löst einen [COleException verfügt](../../mfc/reference/coleexception-class.md).  
  
 Der Zeiger im Arraydeskriptor ist gültig bis `Unlock` aufgerufen wird. Aufrufe von `Lock` können geschachtelt sein; eine gleiche Anzahl von Aufrufen an `Unlock` erforderlich sind.  
  
 Ein Array kann nicht gelöscht werden, solange sie gesperrt ist.  
  
##  <a name="a-nameoperatorlpcvarianta--colesafearrayoperator-lpcvariant"></a><a name="operator_lpcvariant"></a>COleSafeArray::operator LPCVARIANT  
 Rufen Sie diese Umwandlungsoperator für den Zugriff auf die zugrunde liegende **VARIANT** Struktur für dieses `COleSafeArray` Objekt.  
  
```  
operator LPCVARIANT() const;  
```  
  
##  <a name="a-nameoperatorlpvarianta--colesafearrayoperator-lpvariant"></a><a name="operator_lpvariant"></a>COleSafeArray::operator LPVARIANT  
 Rufen Sie diese Umwandlungsoperator für den Zugriff auf die zugrunde liegende **VARIANT** Struktur für dieses `COleSafeArray` Objekt.  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass das Ändern des Werts in der **VARIANT** Zugriff auf der Zeiger verweist, die von dieser Funktion zurückgegebenen Struktur ändert sich den Wert dieses `COleSafeArray` Objekt.  
  
##  <a name="a-nameoperatoreqa--colesafearrayoperator-"></a><a name="operator_eq"></a>COleSafeArray::operator =  
 Diese überladenen Zuweisungsoperatoren kopieren den Quellwert in diesen `COleSafeArray` Objekt.  
  
```  
COleSafeArray& operator=(const COleSafeArray& saSrc);  
COleSafeArray& operator=(const VARIANT& varSrc);  
  COleSafeArray& operator=(LPCVARIANT pSrc);  
COleSafeArray& operator=(const COleVariant& varSrc);
```  
  
### <a name="remarks"></a>Hinweise  
 Eine kurze Beschreibung der einzelnen Operatoren folgt:  
  
- **Operator = (** *SaSrc* **)** kopiert eine vorhandene `COleSafeArray` Objekt in dieses Objekt.  
  
- **Operator = (** *VarSrc***)** kopiert eine vorhandene **VARIANT** oder `COleVariant` Array in dieses Objekt.  
  
- **Operator = (** `pSrc` **)** Kopien der **VARIANT** Array-Objekt zugegriffen `pSrc` in dieses Objekt.  
  
##  <a name="a-nameoperatoreqeqa--colesafearrayoperator-"></a><a name="operator_eq_eq"></a>COleSafeArray::operator ==  
 Dieser Operator vergleicht zwei Arrays ( **SAFEARRAY**, **VARIANT**, `COleVariant`, oder `COleSafeArray` Arrays) und gibt einen Wert ungleich NULL, wenn sie gleich; andernfalls 0 sind zurück.  
  
```  
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;  
   
BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;  
   
BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;  ```  
  
### Remarks  
 Two arrays are equal if they have an equal number of dimensions, equal size in each dimension, and equal element values.  
  
##  <a name="operator_lt_lt"></a>  COleSafeArray::operator &lt;&lt;  
 The `COleSafeArray` insertion (<<) operator supports diagnostic dumping and storing of a `COleSafeArray` object to an archive.  
  
```  
CDumpContext & AFXAPI-operator<( CDumpContext& dc, cdumpcontext&=""></( CDumpContext& dc,>  
    COleSafeArray & SaSrc);
```  
  
##  <a name="ptrofindex"></a>  COleSafeArray::PtrOfIndex  
 Returns a pointer to the element specified by the index values.  
  
```  
void PtrOfIndex (long* RgIndices void** PpvData);
```  
  
### Parameters  
 `rgIndices`  
 An array of index values that identify an element of the array. All indexes for the element must be specified.  
  
 `ppvData`  
 On return, pointer to the element identified by the values in `rgIndices`.  
  
##  <a name="putelement"></a>  COleSafeArray::PutElement  
 Assigns a single element into the array.  
  
```  
void PutElement (long* RgIndices void* PvData);
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
void Redim (SAFEARRAYBOUND * PsaboundNew);
```  
  
### Parameters  
 *psaboundNew*  
 Pointer to a new safe array bound structure containing the new array bound. Only the least significant dimension of an array may be changed.  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="resizeonedim"></a>  COleSafeArray::ResizeOneDim  
 Changes the number of elements in a one-dimensional `COleSafeArray` object.  
  
```  
void ResizeOneDim (DWORD DwElements);
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
void UnaccessData();
```  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
  See the example for [COleSafeArray::AccessData](#accessdata).  
  
##  <a name="unlock"></a>  COleSafeArray::Unlock  
 Decrements the lock count of an array so it can be freed or resized.  
  
```  
void Unlock();
```  
  
### Remarks  
 This function is called after access to the data in an array is finished. On error, it throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
## See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)

