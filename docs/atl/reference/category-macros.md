---
title: Kategorie Makros | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlGetHexValue
- atlbase/ATL::AtlGetVersion
- atlenc/ATL::AtlHexDecode
- atlenc/ATL::AtlHexDecodeGetRequiredLength
- atlenc/ATL::AtlHexEncode
- atlenc/ATL::AtlHexEncodeGetRequiredLength
- atlenc/ATL::AtlHexValue
- atlenc/ATL::BEncode
- atlenc/ATL::BEncodeGetRequiredLength
- atlenc/ATL::EscapeXML
- atlenc/ATL::GetExtendedChars
- atlenc/ATL::IsExtendedChar
- atlenc/ATL::QEncode
- atlenc/ATL::QEncodeGetRequiredLength
- atlenc/ATL::QPDecode
- atlenc/ATL::QPDecodeGetRequiredLength
- atlenc/ATL::QPEncode
- atlenc/ATL::QPEncodeGetRequiredLength
- atlenc/ATL::UUDecode
- atlenc/ATL::UUDecodeGetRequiredLength
- atlenc/ATL::UUEncode
- atlenc/ATL::UUEncodeGetRequiredLength
dev_langs:
- C++
ms.assetid: 223578cb-6180-4787-a8d8-ba3787a5d3ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1eba97ef5253041752d4b8abfcd6ea7300b8492
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="category-macros"></a>Kategorie-Makros
Diese Makros definieren Zuordnungen Kategorie.  
  
|||  
|-|-|  
|[BEGIN_CATEGORY_MAP](#begin_category_map)|Markiert den Beginn der Zuordnung Kategorie.|  
|[END_CATEGORY_MAP](#end_category_map)|Markiert das Ende der Zuordnung Kategorie.|  
|[IMPLEMENTED_CATEGORY](#implemented_category)|Gibt an, Kategorien, die von der COM-Objekt implementiert werden.|  
|[REQUIRED_CATEGORY](#required_category)|Gibt an, Kategorien, die von der COM-Objekt den Container erforderlich sind.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  

##  <a name="begin_category_map"></a>  BEGIN_CATEGORY_MAP  
 Markiert den Beginn der Zuordnung Kategorie.  
  
```
BEGIN_CATEGORY_MAP(theClass)
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 [in] Der Name der Klasse, die die Kategorie-Zuordnung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die Kategorie-Zuordnung wird verwendet, um welche Komponentenkategorien anzugeben, die COM-Klasse implementiert wird und welche Kategorien aus dem zugehörigen Container erfordert.  
  
 Hinzufügen einer [IMPLEMENTED_CATEGORY](#implemented_category) Eintrag zur Zuordnung für jede Kategorie, die von der COM-Klasse implementiert. Hinzufügen einer [REQUIRED_CATEGORY](#required_category) Eintrag zur Zuordnung für jede Kategorie, die die Klasse seinen Clients implementiert erfordert. Markieren Sie das Ende der Zuordnung mit der [END_CATEGORY_MAP](#end_category_map) Makro.  
  
 Die Komponentenkategorien aufgeführt, die in der Zuordnung werden automatisch registriert werden, wenn das Modul registriert wird, wenn die Klasse ein zugehöriges verfügt [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) oder [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) .  
  
> [!NOTE]
>  ATL verwendet Standardkomponente Kategorien-Managers Komponentenkategorien zu registrieren. Ist der Manager nicht auf dem System vorhanden, wenn das Modul registriert ist, Registrierung ist erfolgreich, aber die Komponentenkategorien werden für diese Klasse nicht registriert werden.  
  
 Weitere Informationen zu den Komponentenkategorien finden Sie unter [was Komponentenkategorien sind und wie Arbeiten sie](http://msdn.microsoft.com/library/windows/desktop/ms694322) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="end_category_map"></a>  END_CATEGORY_MAP  
 Markiert das Ende der Zuordnung Kategorie.  
  
```
END_CATEGORY_MAP()
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_CATEGORY_MAP](#begin_category_map).  
  
##  <a name="implemented_category"></a>  IMPLEMENTED_CATEGORY  
 Hinzufügen einer `IMPLEMENTED_CATEGORY` Makro für Ihre Komponentennamens [Kategorie Zuordnung](#begin_category_map) um anzugeben, dass es registriert werden soll, als die Kategorie identifizierte implementieren die `catID` Parameter.  
  
```
IMPLEMENTED_CATEGORY(catID)
```  
  
### <a name="parameters"></a>Parameter  
 `catID`  
 [in] Ein **CATID** Konstante oder Variable, die mit den globally unique Identifier (GUID) für die implementierten Kategorie. Die Adresse des `catID` entnommen und dem Schema hinzugefügt. Siehe folgende Tabelle für eine Reihe von vordefinierten Kategorien an.  
  
### <a name="remarks"></a>Hinweise  
 Die Komponentenkategorien aufgeführt, die in der Zuordnung werden automatisch registriert werden, wenn das Modul registriert wird, wenn die Klasse ein zugehöriges verfügt [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) oder [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) Makro.  
  
 Clients können die Kategorieinformationen registriert, die für die Klasse verwenden, um seine Funktionen und Anforderungen zu ermitteln, ohne eine Instanz erstellen zu müssen.  
  
 Weitere Informationen zu den Komponentenkategorien finden Sie unter [was Komponentenkategorien sind und wie Arbeiten sie](http://msdn.microsoft.com/library/windows/desktop/ms694322) im Windows SDK.  
  
### <a name="a-selection-of-stock-categories"></a>Eine Auswahl von vordefinierten Kategorien  
  
|Beschreibung|Symbol|GUID-Registrierung|  
|-----------------|------------|-------------------|  
|Sicher für Skripting|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|Sicher für Initialisierung|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|Einfacher Frame-Site-Kapselung|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|einfache Datenbindung|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|Erweiterte Datenbindung|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|Fensterlose Steuerelemente|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|Internet unterstützende Objekte|Finden Sie unter [Internetobjekte](http://msdn.microsoft.com/library/windows/desktop/ms690561) in das Windows SDK für eine Beispielliste.||  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="required_category"></a>  REQUIRED_CATEGORY  
 Hinzufügen einer `REQUIRED_CATEGORY` Makro für Ihre Komponentennamens [Kategorie Zuordnung](#begin_category_map) um anzugeben, dass es erfordern, der Kategorie identifizierte registriert werden soll die `catID` Parameter.  
  
```
REQUIRED_CATEGORY( catID )
```  
  
### <a name="parameters"></a>Parameter  
 `catID`  
 [in] Ein **CATID** Konstante oder Variable, die mit den globally unique Identifier (GUID) für die Anforderungskategorie. Die Adresse des `catID` entnommen und dem Schema hinzugefügt. Siehe folgende Tabelle für eine Reihe von vordefinierten Kategorien an.  
  
### <a name="remarks"></a>Hinweise  
 Die Komponentenkategorien aufgeführt, die in der Zuordnung werden automatisch registriert werden, wenn das Modul registriert wird, wenn die Klasse ein zugehöriges verfügt [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) oder [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) Makro.  
  
 Clients können die Kategorieinformationen registriert, die für die Klasse verwenden, um seine Funktionen und Anforderungen zu ermitteln, ohne eine Instanz erstellen zu müssen. Beispielsweise kann ein Steuerelement die Datenbindung zu ein Container unterstützen erforderlich. Die Container erhalten, wenn sie die Funktionen, die zum Hosten des Steuerelements durch Abfragen des Category-Managers für die Kategorien, die erforderlich sind, indem das entsprechende Steuerelement verfügt. Wenn der Container eine erforderliche Funktion nicht unterstützt, kann es ablehnen zum Hosten des COM-Objekts.  
  
 Weitere Informationen zu Komponentenkategorien, einschließlich einer Beispielliste finden Sie unter [was Komponentenkategorien sind und wie Arbeiten sie](http://msdn.microsoft.com/library/windows/desktop/ms694322) im Windows SDK.  
  
### <a name="a-selection-of-stock-categories"></a>Eine Auswahl von vordefinierten Kategorien  
  
|Beschreibung|Symbol|GUID-Registrierung|  
|-----------------|------------|-------------------|  
|Sicher für Skripting|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|Sicher für Initialisierung|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|Einfacher Frame-Site-Kapselung|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|einfache Datenbindung|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|Erweiterte Datenbindung|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|Fensterlose Steuerelemente|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|Internet unterstützende Objekte|Finden Sie unter [Internetobjekte](http://msdn.microsoft.com/library/windows/desktop/ms690561) in das Windows SDK für eine Beispielliste.||  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#135](../../atl/codesnippet/cpp/category-macros_2.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)
