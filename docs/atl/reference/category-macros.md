---
title: Kategorie-Makros | Microsoft-Dokumentation
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
ms.openlocfilehash: 40fdfa363da286952139248088c737b348873ec8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063678"
---
# <a name="category-macros"></a>Kategorie-Makros

Diese Makros definieren Zuordnungen der Kategorie.

|||
|-|-|
|[BEGIN_CATEGORY_MAP](#begin_category_map)|Markiert den Beginn der Zuordnung Kategorie.|
|[END_CATEGORY_MAP](#end_category_map)|Markiert das Ende der Zuordnung Kategorie.|
|[IMPLEMENTED_CATEGORY](#implemented_category)|Gibt an, Kategorien, die vom COM-Objekt implementiert werden.|
|[REQUIRED_CATEGORY](#required_category)|Gibt an, Kategorien, die von den Container von COM-Objekts erforderlich sind.|

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="begin_category_map"></a>  BEGIN_CATEGORY_MAP

Markiert den Beginn der Zuordnung Kategorie.

```
BEGIN_CATEGORY_MAP(theClass)
```

### <a name="parameters"></a>Parameter

*theClass*<br/>
[in] Der Name der Klasse, die die Kategorie-Zuordnung enthält.

### <a name="remarks"></a>Hinweise

Die Kategorie-Zuordnung wird verwendet, an welche Komponentenkategorien COM-Klasse implementiert, und welche Kategorien von seinem Container erfordert.

Hinzufügen einer [IMPLEMENTED_CATEGORY](#implemented_category) einen Eintrag in der Zuordnung für jede Kategorie von COM-Klasse implementiert. Hinzufügen einer [REQUIRED_CATEGORY](#required_category) einen Eintrag in der Zuordnung für jede Kategorie, die die Klasse, die von Clients implementiert erfordert. Markieren Sie am Ende der Zuordnung mit der [END_CATEGORY_MAP](#end_category_map) Makro.

Die Komponentenkategorien aufgeführt, die in der Zuordnung werden automatisch registriert werden, wenn das Modul registriert wird, wenn die Klasse eine zugeordnete hat [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) oder [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) .

> [!NOTE]
>  ATL verwendet die standard-Komponenten-Kategorien-Managers, um Komponentenkategorien zu registrieren. Ist der Manager nicht auf dem System vorhanden, wenn das Modul registriert wurde, Registrierung ist erfolgreich, aber die Komponentenkategorien werden für diese Klasse nicht registriert werden.

Weitere Informationen zu den Komponentenkategorien finden Sie unter [Was sind die Komponenten-Kategorien und deren Funktionsweise](/windows/desktop/com/component-categories-and-how-they-work) im Windows SDK.

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

Hinzufügen einer IMPLEMENTED_CATEGORY Makros zu Ihrer Komponentennamens zu [Kategorie Zuordnung](#begin_category_map) um anzugeben, dass es registriert werden soll, wie die Implementierung der identifizierte Kategorie der *CatID* Parameter.

```
IMPLEMENTED_CATEGORY(catID)
```

### <a name="parameters"></a>Parameter

*catID*<br/>
[in] Eine CATID-Konstante oder die Variable, die globally unique Identifier (GUID) für die Kategorie "implementiert" enthält. Die Adresse des *CatID* ausgeführt werden und zur Karte hinzugefügt. Siehe Tabelle unten für eine Reihe von vordefinierten Kategorien.

### <a name="remarks"></a>Hinweise

Die Komponentenkategorien aufgeführt, die in der Zuordnung werden automatisch registriert werden, wenn das Modul registriert wird, wenn die Klasse eine zugeordnete hat [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) oder [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) -Makro.

Clients können Informationen über die Kategorie für die Klasse registriert verwenden, um seine Funktionen und Anforderungen zu bestimmen, ohne eine Instanz davon erstellen zu müssen.

Weitere Informationen zu den Komponentenkategorien finden Sie unter [Was sind die Komponenten-Kategorien und deren Funktionsweise](/windows/desktop/com/component-categories-and-how-they-work) im Windows SDK.

### <a name="a-selection-of-stock-categories"></a>Eine Auswahl von vordefinierten Kategorien

|Beschreibung|Symbol|GUID-Registrierung|
|-----------------|------------|-------------------|
|Sicher für Skripting|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|
|Sicher für Initialisierung|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|
|Einfache Frame-Site-Kapselung|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|
|einfache Datenbindung|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|
|Erweiterte Datenbindung|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|
|Fensterlose Steuerelemente|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|
|Internet-Objekte|Finden Sie unter [Internetobjekte](/windows/desktop/com/internet-aware-objects) im Windows SDK für eine Beispielliste.||

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]

##  <a name="required_category"></a>  REQUIRED_CATEGORY

Hinzufügen eines REQUIRED_CATEGORY Makros zu Ihrer Komponentennamens zu [Kategorie Zuordnung](#begin_category_map) um anzugeben, dass es registriert werden soll, erfordert die identifizierte Kategorie der *CatID* Parameter.

```
REQUIRED_CATEGORY( catID )
```

### <a name="parameters"></a>Parameter

*catID*<br/>
[in] Eine CATID-Konstante oder die Variable, die globally unique Identifier (GUID) für die erforderliche Kategorie enthält. Die Adresse des *CatID* ausgeführt werden und zur Karte hinzugefügt. Siehe Tabelle unten für eine Reihe von vordefinierten Kategorien.

### <a name="remarks"></a>Hinweise

Die Komponentenkategorien aufgeführt, die in der Zuordnung werden automatisch registriert werden, wenn das Modul registriert wird, wenn die Klasse eine zugeordnete hat [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) oder [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) -Makro.

Clients können Informationen über die Kategorie für die Klasse registriert verwenden, um seine Funktionen und Anforderungen zu bestimmen, ohne eine Instanz davon erstellen zu müssen. Beispielsweise erfordern ein Steuerelement, dass ein Container die Datenbindung zu unterstützen. Container kann feststellen, wenn sie die Funktionen, die zum Hosten des Steuerelements durch Abfragen der Kategorie-Manager für die Kategorien, die erforderlich sind, indem Sie das Steuerelement enthält. Wenn der Container eine erforderliche Funktion nicht unterstützt, kann es ablehnen, zum Hosten des COM-Objekts.

Weitere Informationen zu den Komponentenkategorien, einschließlich einer Beispielliste finden Sie unter [Was sind die Komponenten-Kategorien und deren Funktionsweise](/windows/desktop/com/component-categories-and-how-they-work) im Windows SDK.

### <a name="a-selection-of-stock-categories"></a>Eine Auswahl von vordefinierten Kategorien

|Beschreibung|Symbol|GUID-Registrierung|
|-----------------|------------|-------------------|
|Sicher für Skripting|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|
|Sicher für Initialisierung|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|
|Einfache Frame-Site-Kapselung|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|
|einfache Datenbindung|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|
|Erweiterte Datenbindung|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|
|Fensterlose Steuerelemente|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|
|Internet-Objekte|Finden Sie unter [Internetobjekte](/windows/desktop/com/internet-aware-objects) im Windows SDK für eine Beispielliste.||

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#135](../../atl/codesnippet/cpp/category-macros_2.h)]

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)
