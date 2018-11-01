---
title: CD2DResource-Klasse
ms.date: 11/04/2016
f1_keywords:
- CD2DResource
- AFXRENDERTARGET/CD2DResource
- AFXRENDERTARGET/CD2DResource::CD2DResource
- AFXRENDERTARGET/CD2DResource::Create
- AFXRENDERTARGET/CD2DResource::Destroy
- AFXRENDERTARGET/CD2DResource::IsValid
- AFXRENDERTARGET/CD2DResource::IsAutoDestroy
- AFXRENDERTARGET/CD2DResource::ReCreate
- AFXRENDERTARGET/CD2DResource::m_bIsAutoDestroy
- AFXRENDERTARGET/CD2DResource::m_pParentTarget
helpviewer_keywords:
- CD2DResource [MFC], CD2DResource
- CD2DResource [MFC], Create
- CD2DResource [MFC], Destroy
- CD2DResource [MFC], IsValid
- CD2DResource [MFC], IsAutoDestroy
- CD2DResource [MFC], ReCreate
- CD2DResource [MFC], m_bIsAutoDestroy
- CD2DResource [MFC], m_pParentTarget
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
ms.openlocfilehash: a4846fb8ea34a3d6a83ae892eabee74f4a48cd6a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586376"
---
# <a name="cd2dresource-class"></a>CD2DResource-Klasse

Eine abstrakte Klasse, die eine Schnittstelle zum Erstellen und Verwalten von D2D-Ressourcen wie z. B. Pinsel, Ebenen und Texte enthält.

## <a name="syntax"></a>Syntax

```
class CD2DResource : public CObject;
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DResource::CD2DResource](#cd2dresource)|Erstellt ein CD2DResource-Objekt.|
|[CD2DResource:: ~ CD2DResource](#cd2dresource__~cd2dresource)|Der Destruktor. Wird aufgerufen, wenn ein Ressourcenobjekt auf D2D zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DResource:: Create](#create)|Erstellt eine CD2DResource an.|
|[CD2DResource:: Destroy](#destroy)|Zerstört ein CD2DResource-Objekt.|
|[CD2DResource::IsValid](#isvalid)|Die Gültigkeit der Überprüfungen-Ressource|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DResource::IsAutoDestroy](#isautodestroy)|Kontrollkästchen automatisch zerstört Flag.|
|[CD2DResource::ReCreate](#recreate)|Wird Sie einer CD2DResource neu erstellt.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CD2DResource::m_bIsAutoDestroy](#m_bisautodestroy)|Ressource wird Destoyed vom Besitzer (CRenderTarget) sein.|
|[CD2DResource::m_pParentTarget](#m_pparenttarget)|Zeiger auf das übergeordnete Element CRenderTarget)|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CD2DResource`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="_dtorcd2dresource"></a>  CD2DResource:: ~ CD2DResource

Der Destruktor. Wird aufgerufen, wenn ein Ressourcenobjekt auf D2D zerstört wird.

```
virtual ~CD2DResource();
```

##  <a name="cd2dresource"></a>  CD2DResource::CD2DResource

Erstellt ein CD2DResource-Objekt.

```
CD2DResource(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy);
```

### <a name="parameters"></a>Parameter

*pParentTarget*<br/>
Ein Zeiger auf das Renderziel.

*bAutoDestroy*<br/>
Gibt an, dass vom Besitzer (pParentTarget) das Objekt zerstört wird.

##  <a name="create"></a>  CD2DResource:: Create

Erstellt eine CD2DResource an.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;
```

### <a name="parameters"></a>Parameter

*pRenderTarget*<br/>
Ein Zeiger auf das Renderziel.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

##  <a name="destroy"></a>  CD2DResource:: Destroy

Zerstört ein CD2DResource-Objekt.

```
virtual void Destroy() = 0;
```

##  <a name="isautodestroy"></a>  CD2DResource::IsAutoDestroy

Kontrollkästchen automatisch zerstört Flag.

```
BOOL IsAutoDestroy() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn das Objekt von seinem Besitzer zerstört wird. andernfalls "false".

##  <a name="isvalid"></a>  CD2DResource::IsValid

Die Gültigkeit der Überprüfungen-Ressource

```
virtual BOOL IsValid() const = 0;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Ressource gültig ist. andernfalls "false".

##  <a name="m_bisautodestroy"></a>  CD2DResource::m_bIsAutoDestroy

Ressource wird Destoyed vom Besitzer (CRenderTarget) sein.

```
BOOL m_bIsAutoDestroy;
```

##  <a name="m_pparenttarget"></a>  CD2DResource::m_pParentTarget

Zeiger auf das übergeordnete Element CRenderTarget)

```
CRenderTarget* m_pParentTarget;
```

##  <a name="recreate"></a>  CD2DResource::ReCreate

Wird Sie einer CD2DResource neu erstellt.

```
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parameter

*pRenderTarget*<br/>
Ein Zeiger auf das Renderziel.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
