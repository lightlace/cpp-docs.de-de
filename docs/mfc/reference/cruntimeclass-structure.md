---
title: CRuntimeClass Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- CRuntimeClass structure
- dynamic class information
- runtime, class information
- run-time class, CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 17994895aec5eee3fbe67bef5f80494988906df9
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cruntimeclass-structure"></a>CRuntimeClass-Struktur
Jede Klasse abgeleitet `CObject` zugeordnet ist eine `CRuntimeClass` -Struktur, die Sie verwenden können, um Informationen über ein Objekt oder ihre Basisklasse zur Laufzeit abzurufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CRuntimeClass  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRuntimeClass::CreateObject](#createobject)|Erstellt ein Objekt zur Laufzeit.|  
|[CRuntimeClass](#fromname)|Erstellt ein Objekt zur Laufzeit über den Klassennamen vertraut.|  
|[CRuntimeClass::IsDerivedFrom](#isderivedfrom)|Bestimmt, ob die Klasse von der angegebenen Klasse abgeleitet ist.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRuntimeClass::m_lpszClassName](#m_lpszclassname)|Der Name der Klasse.|  
|[CRuntimeClass::m_nObjectSize](#m_nobjectsize)|Die Größe des Objekts in Bytes.|  
|[CRuntimeClass::m_pBaseClass](#m_pbaseclass)|Ein Zeiger auf die `CRuntimeClass` Struktur der Basisklasse.|  
|[CRuntimeClass::m_pfnCreateObject](#m_pfncreateobject)|Ein Zeiger auf die Funktion, die das Objekt dynamisch erstellt.|  
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|Gibt die `CRuntimeClass` -Struktur (nur verfügbar, wenn Sie dynamisch verknüpft).|  
|[CRuntimeClass::m_wSchema](#m_wschema)|Die Schema-Anzahl der-Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 `CRuntimeClass`ist eine Struktur, und muss daher keine Basisklasse.  
  
 Die Möglichkeit, die Klasse eines Objekts zur Laufzeit zu bestimmen ist nützlich, wenn zusätzliche Überprüfung von Funktionsargumenten erforderlich ist oder wenn Sie basierend auf der Klasse eines Objekts von speziellen Code schreiben müssen. Laufzeit Klasseninformationen wird direkt von der Programmiersprache C++ nicht unterstützt.  
  
 `CRuntimeClass`enthält Informationen zu den zugehörigen C++-Objekt, z. B. ein Zeiger auf die `CRuntimeClass` von der Basisklasse und den ASCII-Namen der verbundenen Klasse. Diese Struktur implementiert auch verschiedene Funktionen, die verwendet werden können, dynamisch erstellt Objekte, die den Typ des Objekts mit einem Ihnen vertrauten Namen und bestimmen, ob die verknüpfte Klasse aus einer bestimmten Klasse abgeleitet ist.  
  
 Weitere Informationen zur Verwendung von `CRuntimeClass`, finden Sie im Artikel [zugreifen auf Laufzeit-Klasseninformationen](../../mfc/accessing-run-time-class-information.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CRuntimeClass`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="createobject"></a>CRuntimeClass::CreateObject  
 Rufen Sie diese Funktion, um die angegebene Klasse zur Laufzeit dynamisch zu erstellen.  
  
```  
CObject* CreateObject();  
  
static CObject* PASCAL CreateObject(LPCSTR lpszClassName);  
  
static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszClassName`  
 Den tatsächlichen Namen der Klasse erstellt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neu erstellte Objekt oder **NULL** , wenn der Name der Klasse nicht gefunden wird oder nicht genügend zum Erstellen des Objekts Arbeitsspeicher.  
  
### <a name="remarks"></a>Hinweise  
 Abgeleitete Klassen `CObject` unterstützen dynamische Erstellung, also die Möglichkeit, ein Objekt einer bestimmten Klasse zur Laufzeit zu erstellen. Dokument anzeigen und Frameklassen sollte z. B. die dynamische Erstellung unterstützen. Weitere Informationen zum dynamischen Erstellen und die `CreateObject` Element finden Sie unter [CObject-Klasse](../../mfc/using-cobject.md) und [CObject-Klasse: Ebenen von Funktionen angeben](../../mfc/specifying-levels-of-functionality.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="fromname"></a>CRuntimeClass  
 Rufen Sie diese Funktion zum Abrufen der `CRuntimeClass` Struktur, die den tatsächlichen Namen zugeordnet.  
  
```  
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);  
  
static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszClassName`  
 Der bekannte Name einer Klasse abgeleitet `CObject`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CRuntimeClass` Objekt entspricht dem Namen übergeben wurde `lpszClassName`. Gibt die Funktion **NULL** Wenn kein übereinstimmender Klassenname gefunden wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample&17;](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]  
  
##  <a name="isderivedfrom"></a>CRuntimeClass::IsDerivedFrom  
 Mit dieser Funktion können Sie bestimmen, ob die Klasse angegeben wird, die aufrufende Klasse abgeleitet ist die *pBaseClass* Parameter.  
  
```  
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;

 
```  
  
### <a name="parameters"></a>Parameter  
 *pBaseClass*  
 Der bekannte Name einer Klasse abgeleitet `CObject`.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE** Wenn die aufrufende Klasse `IsDerivedFrom` wird abgeleitet aus der Klasse, deren `CRuntimeClass` Struktur ist, andernfalls als Parameter angegebenen **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Die Beziehung wird durch "walking" ganz an den Anfang des Mitglieds-Klasse die Kette von abgeleiteten Klassen bestimmt. Diese Funktion gibt nur **FALSE** Wenn keine Übereinstimmung, für die Basisklasse gefunden wird.  
  
> [!NOTE]
>  Verwenden der `CRuntimeClass` -Struktur, müssen Sie enthalten die `IMPLEMENT_DYNAMIC`, `IMPLEMENT_DYNCREATE`, oder `IMPLEMENT_SERIAL` Makro in der Implementierung der Klasse-Objekt abgerufen werden soll.  
  
 Weitere Informationen zur Verwendung von `CRuntimeClass`, finden Sie im Artikel [CObject-Klasse: Zugreifen auf Laufzeit-Klasseninformationen](../../mfc/accessing-run-time-class-information.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample&18;](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]  
  
##  <a name="m_lpszclassname"></a>CRuntimeClass::m_lpszClassName  
 Eine auf Null endende Zeichenfolge mit dem Namen der ASCII-Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Name kann verwendet werden, zum Erstellen einer Instanz der Klasse mithilfe der `FromName` Member-Funktion.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_nobjectsize"></a>CRuntimeClass::m_nObjectSize  
 Die Größe des Objekts in Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Objekt, zeigen Sie auf den belegten Speicher Datenmember verfügt, ist die Größe dieses Speichers nicht enthalten.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_pbaseclass"></a>CRuntimeClass::m_pBaseClass  
 Wenn Ihre Anwendung statisch mit MFC verknüpft wird, handelt es sich bei diesen Datenmember enthält einen Zeiger auf die `CRuntimeClass` Struktur der Basisklasse.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung dynamisch mit der MFC-Bibliothek verknüpft ist, finden Sie unter [M_pfnGetBaseClass](#m_pfngetbaseclass).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_pfncreateobject"></a>CRuntimeClass::m_pfnCreateObject  
 Ein Funktionszeiger, mit dem Standardkonstruktor, der ein Objekt der Klasse erstellt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger ist nur gültig, wenn die Klasse die dynamische Erstellung unterstützt; die Funktion andernfalls **NULL**.  
  
##  <a name="m_pfngetbaseclass"></a>CRuntimeClass::m_pfnGetBaseClass  
 Wenn Ihre Anwendung die MFC-Bibliothek als gemeinsam genutzte DLL verwendet, zeigt dieses Datenelement an eine Funktion, die zurückgibt die `CRuntimeClass` Struktur der Basisklasse.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung statisch mit der MFC-Bibliothek verknüpft ist, finden Sie unter [M_pBaseClass](#m_pbaseclass).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_wschema"></a>CRuntimeClass::m_wSchema  
 Die Schema-Anzahl (-1 für nicht serialisierbare Klassen).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zum Schema Zahlen, finden Sie unter der [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) Makro.  
  
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




