---
title: CWinFormsView-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWinFormsView
- AFXWINFORMS/CWinFormsView
- AFXWINFORMS/CWinFormsView::CWinFormsView
- AFXWINFORMS/CWinFormsView::GetControl
dev_langs:
- C++
helpviewer_keywords:
- CWinFormsView [MFC], CWinFormsView
- CWinFormsView [MFC], GetControl
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b4d90f2a7f964d264966d5254d051ebddaf2baa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448141"
---
# <a name="cwinformsview-class"></a>CWinFormsView-Klasse

Stellt generische Funktionen zum Hosten eines Windows Forms-Steuerelements als MFC-Ansicht bereit.

## <a name="syntax"></a>Syntax

```
class CWinFormsView : public CView;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CWinFormsView::CWinFormsView](#cwinformsview)|Erstellt ein `CWinFormsView`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CWinFormsView::](#getcontrol)|Ruft einen Zeiger auf das Windows Forms-Steuerelement ab.|

### <a name="public-operators"></a>Öffentliche Operatoren

|name||
|----------|-|
|[CWinFormsView::operator Steuerelement ^](#operator_control)|Wandelt einen Typ ein Zeiger auf ein Windows Forms-Steuerelement.|

## <a name="remarks"></a>Hinweise

MFC verwendet die `CWinFormsView` -Klasse zum Hosten eines .NET Framework Windows Forms-Steuerelements in MFC-Ansicht. Das Steuerelement ist ein untergeordnetes Element der einheitlichen Ansicht und nimmt den gesamten Clientbereich der MFC-Ansicht. Das Ergebnis ähnelt einer `CFormView` anzeigen, sodass Sie profitieren Sie von der Windows Forms-Designer und Laufzeit für die umfangreiche formularbasierte Ansichten zu erstellen.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

> [!NOTE]
>  MFC-Windows Forms-Integration funktioniert nur in Projekten, die dynamisch mit MFC verknüpfen (Projekte, die in der Bezeichnung definiert ist).

> [!NOTE]
>  CWinFormsView unterstützt nicht die MFC-Teilungsfenster ( [CSplitterWnd-Klasse](../../mfc/reference/csplitterwnd-class.md)). Derzeit nur den Windows Forms-Splitter-Steuerelement wird unterstützt.

## <a name="requirements"></a>Anforderungen

**Header:** afxwinforms.h

##  <a name="cwinformsview"></a>  CWinFormsView::CWinFormsView

Erstellt ein `CWinFormsView`-Objekt.

```
CWinFormsView(System::Type^ pManagedViewType);
```

### <a name="parameters"></a>Parameter

*pManagedViewType*<br/>
Ein Zeiger auf den Datentyp des Windows Forms-Steuerelements.

### <a name="example"></a>Beispiel

Im folgenden Beispiel die `CUserView` Klasse erbt von `CWinFormsView` und übergibt den `UserControl1` auf die `CWinFormsView` Konstruktor. `UserControl1` ist eine benutzerdefinierte Steuerelement im ControlLibrary1.dll.

[!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]

[!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]

##  <a name="getcontrol"></a>  CWinFormsView::

Ruft einen Zeiger auf das Windows Forms-Steuerelement ab.

```
System::Windows::Forms::Control^ GetControl() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine `System.Windows.Forms.Control` Objekt.

### <a name="remarks"></a>Hinweise

Ein Beispiel zur Verwendung von Windows Forms finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="operator_control"></a>  CWinFormsView::operator Steuerelement ^

Wandelt einen Typ ein Zeiger auf ein Windows Forms-Steuerelement.

```
operator System::Windows::Forms::Control^() const;
```

### <a name="remarks"></a>Hinweise

Dieser Operator ermöglicht die Übergabe einer `CWinFormsView` Ansicht, um Funktionen, die einen Zeiger auf ein Windows Forms-Steuerelement des Typs akzeptieren <xref:System.Windows.Forms.Control>.

### <a name="example"></a>Beispiel

  Finden Sie unter [CWinFormsView::](#getcontrol).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWinFormsControl-Klasse](../../mfc/reference/cwinformscontrol-class.md)<br/>
[CWinFormsDialog-Klasse](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CFormView-Klasse](../../mfc/reference/cformview-class.md)
