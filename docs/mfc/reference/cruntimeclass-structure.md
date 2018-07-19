---
title: CRuntimeClass-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84597f8d728b0781231cc07b84ad91495b870437
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852086"
---
# <a name="cruntimeclass-structure"></a>CRuntimeClass-Struktur
Jede Klasse abgeleitet `CObject` zugeordnet ist eine `CRuntimeClass` -Struktur, die Sie verwenden können, um Informationen über ein Objekt oder ihre Basisklasse zur Laufzeit abzurufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CRuntimeClass  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRuntimeClass::CreateObject](#createobject)|Erstellt ein Objekt während der Laufzeit.|  
|[CRuntimeClass](#fromname)|Erstellt ein Objekt während der Laufzeit über den vertrauten Klassennamen.|  
|[CRuntimeClass::IsDerivedFrom](#isderivedfrom)|Bestimmt, ob die Klasse aus der angegebenen Klasse abgeleitet ist.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRuntimeClass::m_lpszClassName](#m_lpszclassname)|Der Name der Klasse.|  
|[CRuntimeClass::m_nObjectSize](#m_nobjectsize)|Die Größe des Objekts in Bytes.|  
|[CRuntimeClass::m_pBaseClass](#m_pbaseclass)|Ein Zeiger auf die `CRuntimeClass` Struktur der Basisklasse.|  
|[CRuntimeClass::m_pfnCreateObject](#m_pfncreateobject)|Ein Zeiger auf die Funktion, die das Objekt dynamisch erstellt.|  
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|Gibt die `CRuntimeClass` -Struktur (nur verfügbar, wenn dynamisch verknüpft).|  
|[CRuntimeClass::m_wSchema](#m_wschema)|Die Schema-Anzahl der-Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 `CRuntimeClass` ist eine Struktur, und daher keine Basisklasse haben.  
  
 Die Möglichkeit, die die Klasse eines Objekts zur Laufzeit zu bestimmen ist nützlich, wenn es sich bei zusätzlichen typüberprüfung von Funktionsargumenten erforderlich ist, oder wenn Sie basierend auf der Klasse eines Objekts von speziellen Code schreiben müssen. Laufzeit Klasseninformationen wird direkt von der Programmiersprache C++ nicht unterstützt.  
  
 `CRuntimeClass` enthält Informationen zu den zugehörigen C++-Objekt, z. B. ein Zeiger auf die `CRuntimeClass` von der Basisklasse und der ASCII-Klassenname der entsprechenden Klasse. Diese Struktur implementiert auch verschiedene Funktionen, die verwendet werden können, zum dynamischen Erstellen von Objekten, das den Typ des Objekts angibt, indem Sie einen bekannten Namen und bestimmen, ob die verknüpfte Klasse aus einer bestimmten Klasse abgeleitet ist.  
  
 Weitere Informationen zur Verwendung von `CRuntimeClass`, finden Sie im Artikel [zugreifen auf Laufzeit-Klasseninformationen](../../mfc/accessing-run-time-class-information.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CRuntimeClass`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="createobject"></a>  CRuntimeClass::CreateObject  
 Rufen Sie diese Funktion, um die angegebene Klasse während der Laufzeit dynamisch zu erstellen.  
  
```  
CObject* CreateObject();  
  
static CObject* PASCAL CreateObject(LPCSTR lpszClassName);  
  
static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>Parameter  
 *"lpszclassname"*  
 Der bekannte Name der Klasse erstellt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neu erstellte Objekt oder NULL, wenn Sie den Namen der Klasse nicht gefunden wird oder nicht genügend Arbeitsspeicher zum Erstellen des Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Von abgeleiteten Klassen `CObject` unterstützen dynamic erstellen, über die die Möglichkeit, ein Objekt einer bestimmten Klasse zur Laufzeit zu erstellen ist. Dokument, Ansicht und dem Frameklassen, sollte z. B. die dynamische Erstellung unterstützen. Weitere Informationen zum dynamischen Erstellen und die `CreateObject` Member finden Sie unter [CObject-Klasse](../../mfc/using-cobject.md) und [CObject-Klasse: Ebenen von Funktionen angeben](../../mfc/specifying-levels-of-functionality.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="fromname"></a>  CRuntimeClass  
 Mit dieser Funktion wird zum Abrufen der `CRuntimeClass` Struktur, die die bekannten Namen zugeordnet.  
  
```  
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);  
  
static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>Parameter  
 *"lpszclassname"*  
 Der bekannte Name einer Klasse abgeleitet `CObject`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CRuntimeClass` entspricht dem Namen wie übergebene Objekt *"lpszclassname"*. Die Funktion gibt NULL zurück, wenn kein übereinstimmender Klassenname nicht gefunden wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]  
  
##  <a name="isderivedfrom"></a>  CRuntimeClass::IsDerivedFrom  
 Mit dieser Funktion können Sie bestimmen, ob die Klasse angegeben, die aufrufende Klasse abgeleitet wird die *pBaseClass* Parameter.  
  
```  
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;

 
```  
  
### <a name="parameters"></a>Parameter  
 *pBaseClass*  
 Der bekannte Name einer Klasse abgeleitet `CObject`.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der aufrufenden Klasse `IsDerivedFrom` wird von der Basisklasse abgeleitete Klasse, deren `CRuntimeClass` Struktur wird als Parameter angegebenen; andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Die Beziehung wird festgelegt, "detailliert" ganz nach oben aus des Mitglieds-Klasse die Kette der abgeleiteten Klassen. Diese Funktion gibt nur "false" zurück, wenn keine Übereinstimmung, für die Basisklasse gefunden wird.  
  
> [!NOTE]
>  Verwenden der `CRuntimeClass` Struktur, müssen Sie das IMPLEMENT_DYNAMIC IMPLEMENT_DYNCREATE oder IMPLEMENT_SERIAL-Makro in der Implementierung der Klasse für den abzurufenden objektmodelldienste zur Laufzeit Informationen einschließen.  
  
 Weitere Informationen zur Verwendung von `CRuntimeClass`, finden Sie im Artikel [CObject-Klasse: Zugreifen auf Laufzeit-Klasseninformationen](../../mfc/accessing-run-time-class-information.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]  
  
##  <a name="m_lpszclassname"></a>  CRuntimeClass::m_lpszClassName  
 Eine mit Null endende Zeichenfolge, die den Namen der ASCII-Klasse enthält.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Name kann verwendet werden, zum Erstellen einer Instanz der Klasse mit dem `FromName` Member-Funktion.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_nobjectsize"></a>  CRuntimeClass::m_nObjectSize  
 Die Größe des Objekts in Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Objekt, zeigen Sie auf zugewiesenen Speicher Datenmember verfügt, ist die Größe der, dass der Speicher nicht enthalten.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_pbaseclass"></a>  CRuntimeClass::m_pBaseClass  
 Wenn Ihre Anwendung statisch mit MFC verknüpft wird, wird dieses Datenelement enthält einen Zeiger auf die `CRuntimeClass` Struktur der Basisklasse.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung dynamisch mit MFC-Bibliothek verknüpft ist, finden Sie unter [M_pfnGetBaseClass](#m_pfngetbaseclass).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_pfncreateobject"></a>  CRuntimeClass::m_pfnCreateObject  
 Ein Funktionszeiger, um den Standardkonstruktor, der ein Objekt der Klasse erstellt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger ist nur gültig, wenn die Klasse, die dynamische Erstellung unterstützt; andernfalls gibt die Funktion NULL zurück.  
  
##  <a name="m_pfngetbaseclass"></a>  CRuntimeClass::m_pfnGetBaseClass  
 Wenn Ihre Anwendung die MFC-Bibliothek als eine freigegebene DLL verwendet, wird dieses Datenelement an eine Funktion, die zurückgibt verweist die `CRuntimeClass` Struktur der Basisklasse.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung statisch mit MFC-Bibliothek verknüpft ist, finden Sie unter [M_pBaseClass](#m_pbaseclass).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_wschema"></a>  CRuntimeClass::m_wSchema  
 Die Schema-Anzahl (-1 für nicht serialisierbare Klassen).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zum Schema Zahlen, finden Sie unter den [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CObject::GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)   
 [CObject:: IsKindOf](../../mfc/reference/cobject-class.md#iskindof)   
 [RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)   
 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)   
 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)   
 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)



