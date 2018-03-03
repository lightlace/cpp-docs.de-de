---
title: Objekt-Zuordnungsmakros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
dev_langs:
- C++
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 626744eb9f2d9dbe6a013bd329406150af35ecca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="object-map-macros"></a>Objekt-Zuordnungsmakros
Diese Makros definieren Objekt Karten und Einträge.  
  
|||  
|-|-|  
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|Ermöglicht Ihnen die Angabe eines Klassenobjekts Beschreibung, die in der objektzuordnung eingegeben wird.|  
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|Ein ATL-Objekt in der objektzuordnung gelangt, wird ein Update der Registrierung und erstellt eine Instanz des Objekts.|  
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|Ermöglicht es Ihnen, anzugeben, dass das Objekt registriert und initialisiert werden sollte, jedoch nicht extern über `CoCreateInstance` erstellbar sein sollte.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
   
##  <a name="declare_object_description"></a>DECLARE_OBJECT_DESCRIPTION  
 Können Sie eine Beschreibung für das Klassenobjekt angeben.  
  
```
DECLARE_OBJECT_DESCRIPTION( x )
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 [in] Beschreibung für das Klassenobjekt.  
  
### <a name="remarks"></a>Hinweise  
 ATL trägt diese Beschreibung in der objektzuordnung über die [OBJECT_ENTRY](http://msdn.microsoft.com/en-us/abd10ee2-54f0-4f94-9ec2-ddf8f4c8c8cd) Makro.  
  
 `DECLARE_OBJECT_DESCRIPTION`implementiert eine `GetObjectDescription` -Funktion, die Sie verwenden können, überschreiben die [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription) Methode.  

  
 Die `GetObjectDescription` Funktion wird aufgerufen, indem **IComponentRegistrar::GetComponents**. **IComponentRegistrar** ist eine Automatisierungsschnittstelle, mit der Sie beim Registrieren und Aufheben der einzelne Komponenten in einer DLL. Wenn Sie eine Komponente Registrierungsstelle-Objekt mit dem ATL-Projekt-Assistenten erstellen, wird der Assistent automatisch implementieren die **IComponentRegistrar** Schnittstelle. **IComponentRegistrar** wird meist von Microsoft Transaction Server verwendet.  
  
 Weitere Informationen über ATL-Projektassistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]  
  
##  <a name="object_entry_auto"></a>OBJECT_ENTRY_AUTO  
 Ein ATL-Objekt in der objektzuordnung gelangt, wird ein Update der Registrierung und erstellt eine Instanz des Objekts.  
  
```
OBJECT_ENTRY_AUTO( clsid, class )
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 [in] Die CLSID der durch die C++-Klasse mit dem Namen `class` implementierten COM-Klasse.  
  
 `class`  
 [in] Der Name der C++-Klasse, die die COM-Klasse implementiert, die durch die `clsid` dargestellt wird.  
  
### <a name="remarks"></a>Hinweise  
 Objekt-Eintragsmakros befinden sich im globalen Gültigkeitsbereich des Projekts, um Unterstützung für die Registrierung, Initialisierung und Erstellung einer neuen Klasse bereitzustellen.  
  
 `OBJECT_ENTRY_AUTO`Gibt die Funktionszeiger der Klasse des projektverbindungserstellers und ClassFactory Klasse des projektverbindungserstellers `CreateInstance` Funktionen für dieses Objekt in die Zuordnung der automatisch generierten ATL-Objekt. Wenn [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver) wird aufgerufen, für jedes Objekt in der objektzuordnung der systemregistrierung aktualisiert.  

  
 In der folgenden Tabelle wird beschrieben, wie die Informationen zur objektzuordnung aus der Klasse, die als zweiter Parameter angegeben wird, um dieses Makro abgerufen wird.  
  
|Informationen zu|Abgerufenes|  
|---------------------|-------------------|  
|COM-Registrierung|[Registrierungsmakros](../../atl/reference/registry-macros.md)|  
|Erstellung von kanalfactorys|[Factory-Makros](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|Instanzerstellung|[Aggregationsmakros](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|Die Registrierung der Komponente-Kategorie|[Kategorie-Makros](../../atl/reference/category-macros.md)|  
|Auf Klassenebene Initialisierung und Bereinigung|[ObjectMain](ccomobjectrootex-class.md#objectmain)|  

  
##  <a name="object_entry_non_createable_ex_auto"></a>OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO  
 Ermöglicht es Ihnen, anzugeben, dass das Objekt registriert und initialisiert werden sollte, jedoch nicht extern über `CoCreateInstance` erstellbar sein sollte.  
  
```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 [in] Die CLSID der durch die C++-Klasse mit dem Namen `class` implementierten COM-Klasse.  
  
 `class`  
 [in] Der Name der C++-Klasse, die die COM-Klasse implementiert, die durch die `clsid` dargestellt wird.  
  
### <a name="remarks"></a>Hinweise  
 Objekt-Eintragsmakros befinden sich im globalen Gültigkeitsbereich des Projekts, um Unterstützung für die Registrierung, Initialisierung und Erstellung einer neuen Klasse bereitzustellen.  
  
 `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO`können Sie angeben, dass ein Objekt registriert und initialisiert werden soll (finden Sie unter [OBJECT_ENTRY_AUTO](#object_entry_auto) für Weitere Informationen), es sollte jedoch nicht über erstellbar `CoCreateInstance`.  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)
