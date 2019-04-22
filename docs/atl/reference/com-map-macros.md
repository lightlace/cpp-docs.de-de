---
title: COM-Zuordnungs-Makros
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
ms.openlocfilehash: 3159a53b5a500aa61b85cf2bc5a97d321ed6ebb5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58772370"
---
# <a name="com-map-macros"></a>COM-Zuordnungs-Makros

Diese Makros definieren Zuordnungen von COM-Schnittstelle.

|||
|-|-|
|[BEGIN_COM_MAP](#begin_com_map)|Markiert den Beginn der Zuordnungseintrags-COM-Schnittstelle.|
|[END_COM_MAP](#end_com_map)|Markiert das Ende der Zuordnungseintrags-COM-Schnittstelle.|

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="begin_com_map"></a>  BEGIN_COM_MAP

Die COM-Zuordnung ist der Mechanismus, der für ein Objekt über für einen Client-Schnittstellen bereitstellen `QueryInterface`.

```
BEGIN_COM_MAP(x)
```

### <a name="parameters"></a>Parameter

*w*<br/>
[in] Der Name des Klassenobjekts, den Sie für Schnittstellen bereitstellen.

### <a name="remarks"></a>Hinweise

[CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) Zeiger für Schnittstellen in der COM-Zuordnung zurückgibt. Starten Sie die schnittstellenzuordnung ein, mit der-Makro, fügen Sie Einträge für die einzelnen Schnittstellen mit der [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) Makro oder eine ihrer Varianten, und führen Sie die Zuordnung mit der [END_COM_MAP](#end_com_map) -Makro.

### <a name="example"></a>Beispiel

Von ATL [BEEPER](../../overview/visual-cpp-samples.md) Beispiel:

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

##  <a name="end_com_map"></a>  END_COM_MAP

Beendet die Definition der Zuordnung COM-Schnittstelle.

```
END_COM_MAP()
```

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)<br/>
[Globale COM-Zuordnungs-Funktionen](../../atl/reference/com-map-global-functions.md)
