---
title: ASP, ATL-Assistent für Active Server Page-Komponenten
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.asp.asp
helpviewer_keywords:
- ATL Active Server Page Component Wizard, ASP
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
ms.openlocfilehash: efc82edf00a9bb2f2facbd883ef88f1d093e0133
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290195"
---
# <a name="asp-atl-active-server-page-component-wizard"></a>ASP, ATL-Assistent für Active Server Page-Komponenten

Verwenden Sie auf dieser Seite des ATL-Assistenten für Active Server Page-Komponente, um die optionale Einstellungen angeben, für die Behandlung von Informationen und Zustände, die im Zusammenhang mit der ASP-Komponente.

- **Optionale Methoden**

   Fügt den optionalen ASP-Methoden **OnStartPage** und **OnEndPage**, auf das Objekt. Diese Option muss ausgewählt werden, damit alle Active Server Pages-Objekte festgelegt werden kann. Es ist standardmäßig ausgewählt.

- **OnStartPage/OnEndPage**

   [OnStartPage](https://msdn.microsoft.com/library/ms691624.aspx) wird zum ersten Mal das Skript versucht, Zugriff auf das Objekt aufgerufen. **OnEndPage** wird aufgerufen, wenn das Objekt wurde das Skript zu verarbeiten.

- **Systeminterne-Objekt**

   Sie müssen auswählen, die **OnStartPage/OnEndPage** Option aus, um alle ASP-Objekte festgelegt.

|Option|Beschreibung|
|------------|-----------------|
|**Anforderung**|Bietet Zugriff auf die systeminternen Active Server Pages **anfordern** Objekt. Das Request-Objekt wird verwendet, um eine HTTP-Anforderung zu übergeben.|
|**Antwort**|Bietet Zugriff auf die systeminternen Active Server Pages **Antwort** Objekt. Als Antwort auf eine Anforderung sendet das Antwortobjekt Informationen an den Browser, um den Benutzer anzuzeigen.|
|**Sitzung**|Bietet Zugriff auf die systeminternen Active Server Pages **Sitzung** Objekt. Die **Sitzung** Objekt enthält Informationen über die aktuelle benutzersitzung, z. B. speichern und Abrufen von Statusinformationen.|
|**Anwendung**|Bietet Zugriff auf die systeminternen Active Server Pages **Anwendung** Objekt. Die **Anwendung** Objekt verwaltet Status, der mehrere ASP-Objekte gemeinsam genutzt wird.|
|**Server**|Bietet Zugriff auf die systeminternen Active Server Pages **Server** Objekt. Die **Server** Objekt können Sie andere ASP-Objekte zu erstellen.|

## <a name="see-also"></a>Siehe auch

[ATL-Assistent für Active Server Page-Komponenten](../../atl/reference/atl-active-server-page-component-wizard.md)<br/>
[ATL Active Server Page-Komponente](../../atl/reference/adding-an-atl-active-server-page-component.md)
