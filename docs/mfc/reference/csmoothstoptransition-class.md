---
title: CSmoothStopTransition-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::Create
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_maximumDuration
dev_langs:
- C++
helpviewer_keywords:
- CSmoothStopTransition [MFC], CSmoothStopTransition
- CSmoothStopTransition [MFC], Create
- CSmoothStopTransition [MFC], m_dblFinalValue
- CSmoothStopTransition [MFC], m_maximumDuration
ms.assetid: e1a4b476-6f96-43dd-90db-870a64406b85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db43e550b38778dbbdc34fb6e696129ca767d28f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377751"
---
# <a name="csmoothstoptransition-class"></a>CSmoothStopTransition-Klasse

Kapselt einen Übergang mit weicher Beendigung.

## <a name="syntax"></a>Syntax

```
class CSmoothStopTransition : public CBaseTransition;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSmoothStopTransition::CSmoothStopTransition](#csmoothstoptransition)|Erstellt einen Übergang mit weicher Beendigung und initialisiert die maximale Dauer und den endgültigen Wert.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSmoothStopTransition::Create](#create)|Ruft den Übergangsbibliothek, um gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CSmoothStopTransition::m_dblFinalValue](#m_dblfinalvalue)|Der Wert der Animationsvariablen am Ende des Übergangs.|
|[CSmoothStopTransition::m_maximumDuration](#m_maximumduration)|Die maximale Dauer des Übergangs.|

## <a name="remarks"></a>Hinweise

Ein Übergang mit weicher Beendigung wird verlangsamt, einen angegebenen Endwert erreicht, und es mit einer Geschwindigkeit von 0 (null) erreicht. Die Dauer des Übergangs wird durch die ursprüngliche Geschwindigkeit, den Unterschied zwischen der ersten und letzten Werte, und die angegebene maximale Dauer bestimmt. Wenn es keine Lösung bestehend aus einem einzelnen mit parabelförmiger Bogen ist, erstellt diese Methode einen kubischen Übergang. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, sie mit dem Operator new. Das gekapselte IUIAnimationTransition COM-Objekt wird von CAnimationController:: erst erstellt, ist es auf NULL. Ändern Membervariablen des Typs an, nach der Erstellung dieses COM-Objekt hat keine Auswirkungen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSmoothStopTransition](../../mfc/reference/csmoothstoptransition-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="create"></a>  CSmoothStopTransition::Create

Ruft den Übergangsbibliothek, um gekapselte COM-Übergangsobjekt zu erstellen.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parameter

*pLibrary*<br/>
Ein Zeiger auf den Übergangsbibliothek, die für die Erstellung der standard-Übergänge zuständig ist.

### <a name="return-value"></a>Rückgabewert

True, wenn der Übergang erfolgreich erstellt wurde. andernfalls "false".

##  <a name="csmoothstoptransition"></a>  CSmoothStopTransition::CSmoothStopTransition

Erstellt einen Übergang mit weicher Beendigung und initialisiert die maximale Dauer und den endgültigen Wert.

```
CSmoothStopTransition(
    UI_ANIMATION_SECONDS maximumDuration,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>Parameter

*maximumDuration*<br/>
Die maximale Dauer des Übergangs.

*dblFinalValue*<br/>
Der Wert der Animationsvariablen am Ende des Übergangs.

##  <a name="m_dblfinalvalue"></a>  CSmoothStopTransition::m_dblFinalValue

Der Wert der Animationsvariablen am Ende des Übergangs.

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_maximumduration"></a>  CSmoothStopTransition::m_maximumDuration

Die maximale Dauer des Übergangs.

```
UI_ANIMATION_SECONDS m_maximumDuration;
```

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
