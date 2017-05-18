---
title: Objekt-Zuordnungsmakros | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
caps.latest.revision: 16
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f03ca61c6ab3c550c316b380d34eb5fa4f3b61de
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="object-map-macros"></a>Map-Makros
Diese Makros definieren Objekt Karten und Einträge.  
  
|||  
|-|-|  
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|Können Sie ein Klassenobjekt Beschreibung, angeben, die in die Objekttabelle eingegeben wird.|  
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|Ein ATL-Objekt in die Objekttabelle gelangt, wird die Registrierung und erstellt eine Instanz des Objekts.|  
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|Ermöglicht es Ihnen, anzugeben, dass das Objekt registriert und initialisiert werden sollte, jedoch nicht extern über `CoCreateInstance` erstellbar sein sollte.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
   
##  <a name="declare_object_description"></a>DECLARE_OBJECT_DESCRIPTION  
 Können Sie eine Beschreibung für das Klassenobjekt angeben.  
  
```
DECLARE_OBJECT_DESCRIPTION( x )
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 [in] Beschreibung für das Klassenobjekt.  
  
### <a name="remarks"></a>Hinweise  
 ATL wird diese Beschreibung in die Objekttabelle über die [OBJECT_ENTRY](http://msdn.microsoft.com/en-us/abd10ee2-54f0-4f94-9ec2-ddf8f4c8c8cd) Makro.  
  
 `DECLARE_OBJECT_DESCRIPTION`implementiert eine `GetObjectDescription` -Funktion, die Sie verwenden können, überschreiben die [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription) Methode.  

  
 Die `GetObjectDescription` Funktion wird aufgerufen, indem **IComponentRegistrar::GetComponents**. **IComponentRegistrar** ist eine Automatisierungsschnittstelle, mit der Sie an-und Abmelden einzelne Komponenten in einer DLL. Wenn Sie ein Objekt für die Registrierung der Komponente mit dem Assistenten für ATL-Projekt erstellen, wird automatisch der Assistent implementiert die **IComponentRegistrar** Schnittstelle. **IComponentRegistrar** wird normalerweise von Microsoft Transaction Server verwendet.  
  
 Weitere Informationen über ATL-Projekt-Assistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Windowing&#123;](../../atl/codesnippet/cpp/object-map-macros_1.h)]  
  
##  <a name="object_entry_auto"></a>OBJECT_ENTRY_AUTO  
 Ein ATL-Objekt in die Objekttabelle gelangt, wird die Registrierung und erstellt eine Instanz des Objekts.  
  
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
  
 `OBJECT_ENTRY_AUTO`Gibt die Funktionszeiger von der Klasse der Ersteller und Klassenfactory Ersteller `CreateInstance` Funktionen für dieses Objekt in der Zuordnung der automatisch generierten ATL-Objekt. Wenn [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver) wird aufgerufen, die Registrierung für jedes Objekt in der objektzuordnung aktualisiert.  

  
 In der folgenden Tabelle wird beschrieben, wie die Informationen zur objektzuordnung aus der Klasse, wobei als zweiten Parameter dieses Makro abgerufen wird.  
  
|Informationen für|Abgerufenes|  
|---------------------|-------------------|  
|COM-Registrierung|[Registrierung von Makros](../../atl/reference/registry-macros.md)|  
|Factory erstellen|[Factory-Makros](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|Instanz erstellen|[Aggregationsmakros](../../atl/reference/aggregation-and-class-factory-macros.md)|  
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
  
 `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO`können Sie angeben, dass ein Objekt registriert und initialisiert werden (finden Sie unter [OBJECT_ENTRY_AUTO](#object_entry_auto) für Weitere Informationen), es sollte jedoch nicht über erstellbaren `CoCreateInstance`.  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)

