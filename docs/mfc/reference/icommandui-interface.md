---
title: ICommandUI-Schnittstelle
ms.date: 11/04/2016
f1_keywords:
- ICommandUI
- AFXWINFORMS/ICommandUI
- AFXWINFORMS/icommandui__Check
- AFXWINFORMS/ICommandUI::ContinueRouting
- AFXWINFORMS/ICommandUI::Enabled
- AFXWINFORMS/ICommandUI::ID
- AFXWINFORMS/ICommandUI::Index
- AFXWINFORMS/ICommandUI::Radio
- AFXWINFORMS/ICommandUI::Text
helpviewer_keywords:
- ICommandUI interface [MFC]
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
ms.openlocfilehash: dd5f79b8ecd65428ce1231777fa6632777859a00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467098"
---
# <a name="icommandui-interface"></a>ICommandUI-Schnittstelle

Verwaltet von Befehlen der Benutzeroberfläche.

## <a name="syntax"></a>Syntax

```
interface class ICommandUI
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[icommandui__Check](#check)|Legt die Benutzeroberflächenelemente für diesen Befehl auf den entsprechenden Aktivierungszustand fest.|
|[ICommandUI::ContinueRouting](#continuerouting)|Teilt den Befehlsrouting Mechanismus weiterhin Weiterleitung der aktuellen Nachricht der Vererbungskette von Handlern.|
|[ICommandUI::Enabled](#enabled)|Aktiviert oder deaktiviert die Benutzeroberflächenelemente für diesen Befehl.|
|[ICommandUI::ID](#id)|Ruft die ID des Benutzerobjekts für die Schnittstelle dargestellt, durch die `ICommandUI` Objekt.|
|[ICommandUI::Index](#index)|Ruft den Index des das Benutzeroberflächenobjekt, dargestellt durch die `ICommandUI` Objekt.|
|[ICommandUI::Radio](#radio)|Legt die Benutzeroberflächenelemente für diesen Befehl auf den entsprechenden Aktivierungszustand fest.|
|[ICommandUI::Text](#text)|Legt den Text der Benutzeroberflächenelemente für diesen Befehl fest.|

## <a name="remarks"></a>Hinweise

Diese Schnittstelle bietet Methoden und Eigenschaften, die Befehlen der Benutzeroberfläche zu verwalten. `ICommandUI` ist vergleichbar mit [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md), außer dass `ICommandUI` dient für MFC-Anwendungen, die mit .NET Komponenten zusammenwirken.

`ICommandUI` wird verwendet, in einen ON_UPDATE_COMMAND_UI-Handler in einer [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)-abgeleitete Klasse. Wenn ein Benutzer einer Anwendung (SELECT-Anweisungen oder Klicks) aktiviert wird ein Menü, das jedes Menüelement im angezeigt, als aktiviert oder deaktiviert. Das Ziel der einzelnen Menübefehle im enthält diese Informationen durch einen ON_UPDATE_COMMAND_UI-Handler implementieren. Verwenden Sie das Fenster "Eigenschaften" für jeden Befehl Schnittstelle Benutzerobjekte in Ihrer Anwendung zum Erstellen eines Meldungszuordnungseintrags und Funktionsprototyp für jeden Handler.

Weitere Informationen darüber, wie der `ICommandUI` Schnittstelle wird verwendet, in das Befehlsrouting, finden Sie unter [Vorgehensweise: Hinzufügen Befehlsrouting an der Windows Forms-Steuerelement](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

Weitere Informationen dazu, wie Befehlen der Benutzeroberfläche in MFC verwaltet werden, finden Sie unter [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md).

## <a name="check"></a> ICommandUI::Check

Legt die Benutzeroberflächenelemente für diesen Befehl auf den entsprechenden Aktivierungszustand fest.
```
property UICheckState Check;
```

## <a name="remarks"></a>Hinweise

Diese Eigenschaft legt die Benutzeroberflächenelemente für diesen Befehl auf den entsprechenden Aktivierungszustand an. Überprüfen Sie auf die folgenden Werte festgelegt:
- 0 deaktivieren
- 1 Überprüfen
- Legen Sie unbestimmt 2

## <a name="continuerouting"></a> ICommandUI::ContinueRouting

Weist den Befehl Routingmechanismus dar, um den Vorgang fortzusetzen, routing von der aktuellen Nachricht der Vererbungskette von Handlern.
```
void ContinueRouting();
```

## <a name="remarks"></a>Hinweise

Dies ist eine erweiterte Memberfunktion, die in Verbindung mit einer ON_COMMAND_EX-Handler verwendet werden soll, die FALSE zurückgibt. Weitere Informationen finden Sie im technischen Hinweis TN006: Meldungszuordnungen.

## <a name="enabled"></a> ICommandUI::Enabled

Aktiviert oder deaktiviert die Benutzeroberflächenelemente für diesen Befehl.
```
property bool Enabled;
```

## <a name="remarks"></a>Hinweise

Diese Eigenschaft aktiviert oder deaktiviert die Benutzeroberflächenelemente für diesen Befehl. Legen Sie aktiviert auf "true" aktiviert das Element "false", um ihn zu deaktivieren.

## <a name="id"></a> ICommandUI::ID

Ruft die ID des Benutzerobjekts für die Schnittstelle durch die ICommandUI-Objekt dargestellt wird.
```
property unsigned int ID;
```

## <a name="remarks"></a>Hinweise

Diese Eigenschaft ruft die ID (ein Handle) das Menüelement, Symbolleisten-Schaltfläche oder anderen Benutzeroberflächen-Objekt, das vom ICommandUI-Objekt dargestellt.

## <a name="index"></a> ICommandUI::Index

Ruft den Index des User Interface-Objekts, das vom ICommandUI-Objekt dargestellt.
```
property unsigned int Index;
```

## <a name="remarks"></a>Hinweise

Diese Eigenschaft ruft den Index (ein Handle) das Menüelement, Symbolleisten-Schaltfläche oder anderen Benutzeroberflächen-Objekt, das vom ICommandUI-Objekt dargestellt.

## <a name="radio"></a> ICommandUI::Radio

Legt die Benutzeroberflächenelemente für diesen Befehl auf den entsprechenden Aktivierungszustand fest.
```
property bool Radio;
```

## <a name="remarks"></a>Hinweise

Diese Eigenschaft legt die Benutzeroberflächenelemente für diesen Befehl auf den entsprechenden Aktivierungszustand an. Festlegen der Sender, um "true" aktiviert das Element; andernfalls "false".

## <a name="text"></a> ICommandUI::Text

Legt den Text der Benutzeroberflächenelemente für diesen Befehl fest.
```
property String^ Text;
```

## <a name="remarks"></a>Hinweise

Diese Eigenschaft legt den Text der Benutzeroberflächenelemente für diesen Befehl. Legen Sie Text auf ein Text-Zeichenfolge-Handle.

## <a name="requirements"></a>Anforderungen

**Header:** afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)

## <a name="see-also"></a>Siehe auch

[CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md)
