---
title: Objektzuordnungs-Makros
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
ms.openlocfilehash: 73dc924527bac8499adefab3d0d6b51afa500a5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197379"
---
# <a name="object-map-macros"></a>Objektzuordnungs-Makros

Diese Makros definieren die Objekt-Zuordnungen und Einträge.

|||
|-|-|
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|Ermöglicht Ihnen die Angabe ein Klassenobjekt Beschreibung, die in der objektzuordnung eingegeben wird.|
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|Ein ATL-Objekt in der objektzuordnung gelangt, wird die Registrierung und erstellt eine Instanz des Objekts.|
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|Ermöglicht es Ihnen, anzugeben, dass das Objekt registriert und initialisiert werden sollte, jedoch nicht extern über `CoCreateInstance` erstellbar sein sollte.|

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="declare_object_description"></a>  DECLARE_OBJECT_DESCRIPTION

Können Sie eine textbeschreibung für das Klassenobjekt angeben.

```
DECLARE_OBJECT_DESCRIPTION( x )
```

### <a name="parameters"></a>Parameter

*w*<br/>
[in] Die Klasse die Beschreibung des Objekts.

### <a name="remarks"></a>Hinweise

ATL gibt diese Beschreibung in der objektzuordnung über die [OBJECT_ENTRY_AUTO](#object_entry_auto) Makro.

DECLARE_OBJECT_DESCRIPTION implementiert eine `GetObjectDescription` -Funktion, die Sie verwenden können, überschreiben die [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription) Methode.

Die `GetObjectDescription` Funktion wird aufgerufen, indem `IComponentRegistrar::GetComponents`. `IComponentRegistrar` ist eine Automatisierungsschnittstelle, mit dem Sie an-und Abmelden einzelne Komponenten in einer DLL. Wenn Sie ein Objekt für die Registrierung der Komponente mit dem ATL-Projekt-Assistenten erstellen, wird der Assistent automatisch implementieren die `IComponentRegistrar` Schnittstelle. `IComponentRegistrar` von Microsoft Transaction Server ist in der Regel verwendet werden.

Weitere Informationen über ATL-Projektassistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]

##  <a name="object_entry_auto"></a>  OBJECT_ENTRY_AUTO

Ein ATL-Objekt in der objektzuordnung gelangt, wird die Registrierung und erstellt eine Instanz des Objekts.

```
OBJECT_ENTRY_AUTO( clsid, class )
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
[in] Die CLSID der COM-Klasse implementiert die C++ Klasse mit dem Namen *Klasse*.

*class*<br/>
[in] Der Name des der C++ Klasse implementiert die COM-Klasse, die durch dargestellt *Clsid*.

### <a name="remarks"></a>Hinweise

Objekt-Eintragsmakros befinden sich im globalen Gültigkeitsbereich des Projekts, um Unterstützung für die Registrierung, Initialisierung und Erstellung einer neuen Klasse bereitzustellen.

OBJECT_ENTRY_AUTO eingibt, der Funktionszeiger der Klasse des projektverbindungserstellers und Klassenfactory Klasse des projektverbindungserstellers `CreateInstance` Funktionen für dieses Objekt in die Zuordnung der automatisch generierten ATL-Objekt. Wenn [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver) wird aufgerufen, die Registrierung des Systems für jedes Objekt in der objektzuordnung aktualisiert.

In der folgenden Tabelle wird beschrieben, wie der objektzuordnung hinzugefügten Informationen von der Klasse, die als zweiter Parameter angegeben wird, um dieses Makro abgerufen wird.

|Informationen zu|Abgerufen aus|
|---------------------|-------------------|
|COM-Registrierung|[Registrierungsmakros](../../atl/reference/registry-macros.md)|
|Klasse von Factory-Erstellung|[Klassenfactory-Makros](../../atl/reference/aggregation-and-class-factory-macros.md)|
|Instanzerstellung|[Aggregationsmakros](../../atl/reference/aggregation-and-class-factory-macros.md)|
|Kategorie-komponentenregistrierung|[Kategorie-Makros](../../atl/reference/category-macros.md)|
|Auf Klassenebene Initialisierung und Bereinigung|[ObjectMain](ccomobjectrootex-class.md#objectmain)|

##  <a name="object_entry_non_createable_ex_auto"></a>  OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO

Ermöglicht es Ihnen, anzugeben, dass das Objekt registriert und initialisiert werden sollte, jedoch nicht extern über `CoCreateInstance` erstellbar sein sollte.

```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
[in] Die CLSID der COM-Klasse implementiert die C++ Klasse mit dem Namen *Klasse*.

*class*<br/>
[in] Der Name des der C++ Klasse implementiert die COM-Klasse, die durch dargestellt *Clsid*.

### <a name="remarks"></a>Hinweise

Objekt-Eintragsmakros befinden sich im globalen Gültigkeitsbereich des Projekts, um Unterstützung für die Registrierung, Initialisierung und Erstellung einer neuen Klasse bereitzustellen.

OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO können Sie angeben, dass ein Objekt registriert und initialisiert werden soll (finden Sie unter [OBJECT_ENTRY_AUTO](#object_entry_auto) Informationen), aber es sollte keine erstellbaren über sein `CoCreateInstance`.

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)
