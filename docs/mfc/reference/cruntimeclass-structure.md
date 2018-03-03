---
title: CRuntimeClass Struktur | Microsoft Docs
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
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b053e963f4e252302ed4c390a648846166aff62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cruntimeclass-structure"></a>CRuntimeClass-Struktur
Jede Klasse abgeleitet `CObject` zugeordnet ist eine `CRuntimeClass` -Struktur, die Sie verwenden können, um Informationen über ein Objekt oder seine Basisklasse zur Laufzeit abzurufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CRuntimeClass  
```  
  
## <a name="members"></a>Member  
  
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
|[CRuntimeClass::m_pfnGetBaseClass](#m_pfngetbaseclass)|Gibt die `CRuntimeClass` -Struktur (nur verfügbar, wenn dynamisch verknüpft).|  
|[CRuntimeClass::m_wSchema](#m_wschema)|Die Anzahl der Schema der Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 `CRuntimeClass`ist eine Struktur, und daher keine Basisklasse.  
  
 Kann die Klasse eines Objekts zur Laufzeit bestimmt ist nützlich, wenn zusätzlichen typüberprüfung für Argumente der Funktion benötigt wird oder wenn Sie basierend auf der Klasse eines Objekts zweckgebundene-Code schreiben müssen. Laufzeit Klasseninformationen wird direkt von der Programmiersprache C++ nicht unterstützt.  
  
 `CRuntimeClass`enthält Informationen zu verwandten C++-Objekt, z. B. ein Zeiger auf die `CRuntimeClass` von der Basisklasse und der ASCII-Klassenname für die verknüpfte Klasse aus. Diese Struktur implementiert auch verschiedene Funktionen, die verwendet werden können, zum dynamischen Erstellen von Objekten, das den Typ des Objekts angibt, unter Verwendung eines Namens vertraut sind, und bestimmen, ob die verknüpfte Klasse aus einer bestimmten Klasse abgeleitet wird.  
  
 Weitere Informationen zur Verwendung von `CRuntimeClass`, finden Sie im Artikel [zugreifen auf Laufzeit-Klasseninformationen](../../mfc/accessing-run-time-class-information.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CRuntimeClass`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="createobject"></a>CRuntimeClass::CreateObject  
 Rufen Sie diese Funktion, um die angegebene Klasse während der Laufzeit dynamisch zu erstellen.  
  
```  
CObject* CreateObject();  
  
static CObject* PASCAL CreateObject(LPCSTR lpszClassName);  
  
static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszClassName`  
 Der bekannte Name der Klasse erstellt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neu erstellte Objekt oder **NULL** , wenn der Name der Klasse wurde nicht gefunden, oder es nicht genügend Arbeitsspeicher zum Erstellen des Objekts ist.  
  
### <a name="remarks"></a>Hinweise  
 Abgeleitete Klassen von `CObject` unterstützen die dynamische Erstellung, also die Möglichkeit, ein Objekt einer bestimmten Klasse zur Laufzeit zu erstellen. Dokument anzeigen und Frameklassen sollten z. B. die dynamische Erstellung unterstützen. Weitere Informationen zum dynamischen Erstellen und die `CreateObject` Member finden Sie unter [CObject-Klasse](../../mfc/using-cobject.md) und [CObject-Klasse: Ebenen von Funktionen angeben](../../mfc/specifying-levels-of-functionality.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="fromname"></a>CRuntimeClass  
 Mit dieser Funktion wird zum Abrufen der `CRuntimeClass` Struktur der bekannte Name zugeordnet.  
  
```  
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);  
  
static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszClassName`  
 Der bekannte Name einer Klasse abgeleitet `CObject`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CRuntimeClass` Objekt entspricht dem Namen übergebenen `lpszClassName`. Die Funktion gibt **NULL** , wenn kein übereinstimmender Klassenname gefunden wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]  
  
##  <a name="isderivedfrom"></a>CRuntimeClass::IsDerivedFrom  
 Mit dieser Funktion können Sie bestimmen, ob die Klasse angegeben, die aufrufende Klasse abgeleitet wird die *pBaseClass* Parameter.  
  
```  
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;

 
```  
  
### <a name="parameters"></a>Parameter  
 *pBaseClass*  
 Der bekannte Name einer Klasse abgeleitet `CObject`.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** Wenn aufrufenden Klasse `IsDerivedFrom` wird von der Basisklasse abgeleitete Klasse, deren `CRuntimeClass` Struktur ist andernfalls als Parameter angegebenen **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Die Beziehung wird festgelegt, indem "walking" von der Member-Klasse die Kette von abgeleiteten Klassen ganz nach oben. Diese Funktion nur gibt **"false"** Wenn für die Basisklasse keine Übereinstimmung gefunden wird.  
  
> [!NOTE]
>  Verwenden der `CRuntimeClass` -Struktur, müssen Sie auch die `IMPLEMENT_DYNAMIC`, `IMPLEMENT_DYNCREATE`, oder `IMPLEMENT_SERIAL` Makros in der Implementierung der Klasse für die Laufzeitobjekt-Informationen abgerufen werden sollen.  
  
 Weitere Informationen zur Verwendung von `CRuntimeClass`, finden Sie im Artikel [CObject-Klasse: Zugreifen auf Laufzeit-Klasseninformationen](../../mfc/accessing-run-time-class-information.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]  
  
##  <a name="m_lpszclassname"></a>CRuntimeClass::m_lpszClassName  
 Eine auf Null endende Zeichenfolge, enthält der Name der ASCII-Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Name kann verwendet werden, zum Erstellen einer Instanz der Klasse unter Verwendung der `FromName` Memberfunktion.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_nobjectsize"></a>CRuntimeClass::m_nObjectSize  
 Die Größe des Objekts in Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Objekt, zeigen Sie auf die speicherbelegung Datenmember hat, ist die Größe dieses Speichers nicht enthalten.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_pbaseclass"></a>CRuntimeClass::m_pBaseClass  
 Wenn Ihre Anwendung statisch mit MFC verknüpft ist, wird dieses Datenelement enthält einen Zeiger auf die `CRuntimeClass` Struktur der Basisklasse.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung dynamisch mit MFC-Bibliothek verknüpft ist, finden Sie unter [M_pfnGetBaseClass](#m_pfngetbaseclass).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsDerivedFrom](#isderivedfrom).  
  
##  <a name="m_pfncreateobject"></a>CRuntimeClass::m_pfnCreateObject  
 Ein Funktionszeiger, der Standardkonstruktor, der ein Objekt der Klasse erstellt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger ist nur gültig, wenn die Klasse die dynamische Erstellung unterstützt; die Funktion hingegen gibt **NULL**.  
  
##  <a name="m_pfngetbaseclass"></a>CRuntimeClass::m_pfnGetBaseClass  
 Wenn Ihre Anwendung die MFC-Bibliothek als eine freigegebene DLL verwendet, zeigt dieses Datenelement an eine Funktion, die gibt die `CRuntimeClass` Struktur der Basisklasse.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Ihre Anwendung statisch mit MFC-Bibliothek verknüpft ist, finden Sie unter [M_pBaseClass](#m_pbaseclass).  
  
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



