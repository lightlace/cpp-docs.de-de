---
title: CD2DMesh-Klasse
ms.date: 11/04/2016
f1_keywords:
- CD2DMesh
- AFXRENDERTARGET/CD2DMesh
- AFXRENDERTARGET/CD2DMesh::CD2DMesh
- AFXRENDERTARGET/CD2DMesh::Attach
- AFXRENDERTARGET/CD2DMesh::Create
- AFXRENDERTARGET/CD2DMesh::Destroy
- AFXRENDERTARGET/CD2DMesh::Detach
- AFXRENDERTARGET/CD2DMesh::Get
- AFXRENDERTARGET/CD2DMesh::IsValid
- AFXRENDERTARGET/CD2DMesh::Open
- AFXRENDERTARGET/CD2DMesh::m_pMesh
helpviewer_keywords:
- CD2DMesh [MFC], CD2DMesh
- CD2DMesh [MFC], Attach
- CD2DMesh [MFC], Create
- CD2DMesh [MFC], Destroy
- CD2DMesh [MFC], Detach
- CD2DMesh [MFC], Get
- CD2DMesh [MFC], IsValid
- CD2DMesh [MFC], Open
- CD2DMesh [MFC], m_pMesh
ms.assetid: 11a2c78a-1367-40e8-a34f-44aa0509a4c9
ms.openlocfilehash: f4ad6fd054eeb8576c2fdb2dc924f70034b3abad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396365"
---
# <a name="cd2dmesh-class"></a>CD2DMesh-Klasse

Ein Wrapper für ID2D1Mesh.

## <a name="syntax"></a>Syntax

```
class CD2DMesh : public CD2DResource;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DMesh::CD2DMesh](#cd2dmesh)|Erstellt ein CD2DMesh-Objekt.|
|[CD2DMesh::~CD2DMesh](#_dtorcd2dmesh)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Mesh-Objekt zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DMesh::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle für das Objekt|
|[CD2DMesh::Create](#create)|Erstellt eine CD2DMesh an. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DMesh::Destroy](#destroy)|Zerstört ein CD2DMesh-Objekt. (Überschreibt [CD2DResource:: Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DMesh::Detach](#detach)|Resource-Schnittstelle aus dem Objekt getrennt|
|[CD2DMesh::Get](#get)|Gibt die ID2D1Mesh-Schnittstelle|
|[CD2DMesh::IsValid](#isvalid)|Überprüft die Gültigkeit der Ressource (überschreibt [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DMesh::Open](#open)|Öffnet das Netz zur Auffüllung.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DMesh::Operator ID2D1Mesh *](#operator_id2d1mesh_star)|Gibt die ID2D1Mesh-Schnittstelle|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CD2DMesh::m_pMesh](#m_pmesh)|Ein Zeiger auf ein ID2D1Mesh.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DMesh`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="_dtorcd2dmesh"></a>  CD2DMesh:: ~ CD2DMesh

Der Destruktor. Wird aufgerufen, wenn ein D2D-Mesh-Objekt zerstört wird.

```
virtual ~CD2DMesh();
```

##  <a name="attach"></a>  CD2DMesh::Attach

Hängt die vorhandene Ressourcenschnittstelle für das Objekt

```
void Attach(ID2D1Mesh* pResource);
```

### <a name="parameters"></a>Parameter

*pResource*<br/>
Vorhandene Ressourcenschnittstelle. NULL darf nicht sein

##  <a name="cd2dmesh"></a>  CD2DMesh::CD2DMesh

Erstellt ein CD2DMesh-Objekt.

```
CD2DMesh(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parameter

*pParentTarget*<br/>
Ein Zeiger auf das Renderziel.

*bAutoDestroy*<br/>
Gibt an, dass vom Besitzer (pParentTarget) das Objekt zerstört wird.

##  <a name="create"></a>  CD2DMesh::Create

Erstellt eine CD2DMesh an.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parameter

*pRenderTarget*<br/>
Ein Zeiger auf das Renderziel.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

##  <a name="destroy"></a>  CD2DMesh::Destroy

Zerstört ein CD2DMesh-Objekt.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DMesh::Detach

Resource-Schnittstelle aus dem Objekt getrennt

```
ID2D1Mesh* Detach();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf getrennten Resource-Schnittstelle.

##  <a name="get"></a>  CD2DMesh::Get

Gibt die ID2D1Mesh-Schnittstelle

```
ID2D1Mesh* Get();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1Mesh-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="isvalid"></a>  CD2DMesh::IsValid

Die Gültigkeit der Überprüfungen-Ressource

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Ressource gültig ist. andernfalls "false".

##  <a name="m_pmesh"></a>  CD2DMesh::m_pMesh

Ein Zeiger auf ein ID2D1Mesh.

```
ID2D1Mesh* m_pMesh;
```

##  <a name="open"></a>  CD2DMesh::Open

Öffnet das Netz zur Auffüllung.

```
ID2D1TessellationSink* Open();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein ID2D1TessellationSink, die zum Auffüllen des Netzes verwendet wird.

##  <a name="operator_id2d1mesh_star"></a>  CD2DMesh::Operator ID2D1Mesh *

Gibt die ID2D1Mesh-Schnittstelle

```
operator ID2D1Mesh*();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1Mesh-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
