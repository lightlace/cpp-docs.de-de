---
title: Kategorie-Makros | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 223578cb-6180-4787-a8d8-ba3787a5d3ee
caps.latest.revision: 17
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 26eea5cc8ce8e18af84a9ca89e5ddc94272be44c
ms.lasthandoff: 02/24/2017

---
# <a name="category-macros"></a>Kategorie-Makros
Diese Makros definieren Kategorie zugeordnet.  
  
|||  
|-|-|  
|[BEGIN_CATEGORY_MAP](#begin_category_map)|Markiert den Beginn der Zuordnung Kategorie.|  
|[END_CATEGORY_MAP](#end_category_map)|Markiert das Ende der Zuordnung Kategorie.|  
|[IMPLEMENTED_CATEGORY](#implemented_category)|Gibt die Kategorien, die vom COM-Objekt implementiert werden.|  
|[REQUIRED_CATEGORY](#required_category)|Gibt die Kategorien, die vom COM-Objekt des Containers erforderlich sind.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  

##  <a name="a-namebegincategorymapa--begincategorymap"></a><a name="begin_category_map"></a>BEGIN_CATEGORY_MAP  
 Markiert den Beginn der Zuordnung Kategorie.  
  
```
BEGIN_CATEGORY_MAP(theClass)
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 [in] Der Name der Klasse, die die Zuordnung der Kategorie enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die Kategorie-Zuordnung wird verwendet, welche Komponentenkategorien angeben, die COM-Klasse implementiert wird und welche Kategorien von seinem Container erfordert.  
  
 Hinzufügen einer [IMPLEMENTED_CATEGORY](#implemented_category) Eintrag, um die Zuordnung für jede Kategorie, die von der COM-Klasse implementiert. Hinzufügen einer [REQUIRED_CATEGORY](#required_category) Eintrag, um die Zuordnung für jede Kategorie, die die Klasse implementieren Clients erfordert. Markieren Sie am Ende der Zuordnung mit den [END_CATEGORY_MAP](#end_category_map) Makro.  
  
 Die Komponentenkategorien aufgeführt, die in der Zuordnung werden automatisch registriert werden, wenn das Modul registriert ist, wenn die Klasse eine zugeordnete hat [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) oder [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto).  
  
> [!NOTE]
>  ATL verwendet die standardmäßige Komponentenkategorien-Manager Komponentenkategorien zu registrieren. Ist der Manager nicht auf dem System vorhanden, wenn das Modul registriert ist, Registrierung ist erfolgreich, aber die Komponentenkategorien für diese Klasse nicht registriert.  
  
 Weitere Informationen zu Komponentenkategorien, finden Sie unter [was Komponentenkategorien sind und deren Funktionsweise](http://msdn.microsoft.com/library/windows/desktop/ms694322) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#100;](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="a-nameendcategorymapa--endcategorymap"></a><a name="end_category_map"></a>END_CATEGORY_MAP  
 Markiert das Ende der Zuordnung Kategorie.  
  
```
END_CATEGORY_MAP()
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_CATEGORY_MAP](#begin_category_map).  
  
##  <a name="a-nameimplementedcategorya--implementedcategory"></a><a name="implemented_category"></a>IMPLEMENTED_CATEGORY  
 Hinzufügen einer `IMPLEMENTED_CATEGORY` Makro für Ihre Komponentennamens [Kategorie Karte](#begin_category_map) angegeben wird, dass er registriert werden soll, wie die Implementierung der identifizierte Kategorie der `catID` Parameter.  
  
```
IMPLEMENTED_CATEGORY(catID)
```  
  
### <a name="parameters"></a>Parameter  
 `catID`  
 [in] Ein **CATID** Konstante oder Variable mit den globally unique Identifier (GUID) für die implementierten Kategorie. Die Adresse des `catID` wird erstellt und dem Schema hinzugefügt werden. Finden Sie in der folgenden Tabelle eine Auswahl von vordefinierten Kategorien.  
  
### <a name="remarks"></a>Hinweise  
 Die Komponentenkategorien aufgeführt, die in der Zuordnung werden automatisch registriert werden, wenn das Modul registriert ist, wenn die Klasse eine zugeordnete hat [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) oder [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) Makro.  
  
 Clients können für die Klasse erfasst Informationen zu den Kategorien verwenden, um seine Funktionen und Anforderungen zu ermitteln, ohne eine Instanz davon erstellen zu müssen.  
  
 Weitere Informationen zu Komponentenkategorien, finden Sie unter [was Komponentenkategorien sind und deren Funktionsweise](http://msdn.microsoft.com/library/windows/desktop/ms694322) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="a-selection-of-stock-categories"></a>Eine Auswahl von vordefinierten Kategorien  
  
|Beschreibung|Symbol|Registrierung GUID|  
|-----------------|------------|-------------------|  
|Für Scripting sicher sind|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|Sicher für Initialisierung|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|Einfache Frame Site Containment|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|einfache Datenbindung|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|Erweiterte Bindung|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|Fensterlose Steuerelemente|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|Internet-Objekte|Finden Sie unter [Internetobjekte](http://msdn.microsoft.com/library/windows/desktop/ms690561) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Beispiel-Liste.||  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#100;](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="a-namerequiredcategorya--requiredcategory"></a><a name="required_category"></a>REQUIRED_CATEGORY  
 Hinzufügen einer `REQUIRED_CATEGORY` Makro für Ihre Komponentennamens [Kategorie Karte](#begin_category_map) angeben, dass es erfordern, die Kategorien von registriert werden soll die `catID` Parameter.  
  
```
REQUIRED_CATEGORY( catID )
```  
  
### <a name="parameters"></a>Parameter  
 `catID`  
 [in] Ein **CATID** Konstante oder Variable mit den globally unique Identifier (GUID) für die gewünschte Kategorie. Die Adresse des `catID` wird erstellt und dem Schema hinzugefügt werden. Finden Sie in der folgenden Tabelle eine Auswahl von vordefinierten Kategorien.  
  
### <a name="remarks"></a>Hinweise  
 Die Komponentenkategorien aufgeführt, die in der Zuordnung werden automatisch registriert werden, wenn das Modul registriert ist, wenn die Klasse eine zugeordnete hat [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) oder [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) Makro.  
  
 Clients können für die Klasse erfasst Informationen zu den Kategorien verwenden, um seine Funktionen und Anforderungen zu ermitteln, ohne eine Instanz davon erstellen zu müssen. Z. B. möglicherweise ein Steuerelement, dass ein Container Bindung unterstützen. Container kann herausfinden, ob es die Funktionalität zum Hosten des Steuerelements durch Abfragen der Kategorie-Manager für die Kategorien, die von diesem Steuerelement erforderlich ist. Wenn der Container eine erforderliche Funktion nicht unterstützt, kann es ablehnen zum Hosten des COM-Objekts.  
  
 Weitere Informationen zu Komponentenkategorien, einschließlich einer Beispielliste finden Sie unter [was Komponentenkategorien sind und deren Funktionsweise](http://msdn.microsoft.com/library/windows/desktop/ms694322) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="a-selection-of-stock-categories"></a>Eine Auswahl von vordefinierten Kategorien  
  
|Beschreibung|Symbol|Registrierung GUID|  
|-----------------|------------|-------------------|  
|Für Scripting sicher sind|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|Sicher für Initialisierung|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|Einfache Frame Site Containment|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|einfache Datenbindung|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|Erweiterte Bindung|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|Fensterlose Steuerelemente|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|Internet-Objekte|Finden Sie unter [Internetobjekte](http://msdn.microsoft.com/library/windows/desktop/ms690561) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Beispiel-Liste.||  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#135;](../../atl/codesnippet/cpp/category-macros_2.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)

