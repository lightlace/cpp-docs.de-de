---
title: ATL-Steuerelementkapselung – häufig gestellte Fragen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
- ATL, hosting ActiveX controls
- ActiveX controls [C++], hosting
- controls [ATL]
ms.assetid: d4bdfbe0-82ca-4f2f-bb95-cb89bdcc9b53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28e22df4eba5a12806221beea1966d1c1cdeae46
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052907"
---
# <a name="atl-control-containment-faq"></a>Fragen und Antworten zur ATL-Steuerelementkapselung

## <a name="which-atl-classes-facilitate-activex-control-containment"></a>Welche ATL-Klassen machen die Kapselung von ActiveX-Steuerelement?

Der ATL-steuerelementhostings Code erfordern nicht Ihnen die Verwendung von ATL-Klassen; Erstellen Sie einfach ein **"AtlAxWin80"** und anschließend mit der Steuerelement-hosting-API bei Bedarf (Weitere Informationen finden Sie unter **Neuerungen der ATL-Steuerelement-Hosting-API**. Stellen Sie jedoch die folgenden Klassen die Containment-Features einfacher zu verwenden.

|Klasse|Beschreibung|
|-----------|-----------------|
|[CAxWindow](../atl/reference/caxwindow-class.md)|Umschließt ein **"AtlAxWin80"** Fenster Methoden für das Erstellen des Fensters, erstellen ein Steuerelement und/oder Anfügen eines Steuerelements an das Fenster und Abrufen von Schnittstellenzeigern auf das Hostobjekt bereitstellt.|
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|Umschließt ein **"AtlAxWinLic80"** Fenster Methoden für das Erstellen des Fensters, erstellen ein Steuerelement und/oder ein lizenziertes Steuerelement anfügen, um das Fenster und Abrufen von Schnittstellenzeigern auf das Hostobjekt bereitstellt.|
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|Fungiert als Basisklasse für ActiveX-Steuerelementklassen basierend auf einer Ressource. Solche Steuerelemente können andere ActiveX-Steuerelemente enthalten.|
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|Fungiert als Basisklasse für Klassen basierend auf einer Ressource. Diese Dialogfelder können ActiveX-Steuerelemente enthalten.|
|[CWindow](../atl/reference/cwindow-class.md)|Stellt eine Methode, [GetDlgControl](../atl/reference/cwindow-class.md#getdlgcontrol), einen Schnittstellenzeiger zurückgegeben, für ein Steuerelement anhand der ID des Hostfensters. Darüber hinaus die Windows-API-Wrapper von verfügbar gemachten `CWindow` in der Regel fensterverwaltung erleichtern.|  

## <a name="what-is-the-atl-control-hosting-api"></a>Was ist die ATL-Steuerelement-Hosting-API?

ATL des Steuerelement-hosting-API ist der Satz von Funktionen, die einem beliebigen Fenster, das als ein ActiveX-Steuerelementcontainer fungiert ermöglicht. Diese Funktionen können statisch oder dynamisch in Ihr Projekt verknüpft werden, da sie als Quellcode zur Verfügung stehen und von ATL90.dll verfügbar gemacht werden. Die Steuerelement-hosting-Funktionen sind in der folgenden Tabelle aufgeführt.

|Funktion|Beschreibung|
|--------------|-----------------|
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|Erstellt ein Objekt, mit dem bereitgestellten Fenster verbunden, und fügt ein vorhandenes Steuerelement.|
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|Erstellt ein Objekt, mit dem bereitgestellten Fenster verbunden, und lädt dann ein Steuerelement.|
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster ähnelt [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol).|
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|Erstellt ein Objekt, mit dem bereitgestellten Fenster verbunden und lädt dann ein Steuerelement (auch Ereignissenken um eingerichtet werden können).|
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster ähnelt [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic).|
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|Erstellt ein nicht modales Dialogfeld aus einer Ressource, und gibt das Fensterhandle zurück.|
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|Erstellt ein modales Dialogfeld aus einer Ressource an.|
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|Gibt die **IUnknown** Schnittstellenzeiger des Steuerelements in einem Fenster gehostet.|
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|Gibt die **IUnknown** Schnittstellenzeiger des Hostobjekts an ein Fenster verbunden.|
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|Initialisiert den Steuerelement-hosting-Code.|
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|Hebt die Initialisierung des Steuerelement-hosting-Codes.|

Die `HWND` Parameter in der ersten drei Funktionen müssen ein vorhandenes Fenster (nahezu) in einen beliebigen Typ sein. Wenn Sie eine dieser drei Funktionen explizit aufrufen (in der Regel müssen Sie keine), übergeben Sie ein Handle nicht an ein Fenster, das bereits als Host fungiert (Wenn Sie dies tun, das vorhandene Hostobjekt wird nicht freigegeben werden).

Rufen Sie die ersten sieben Funktionen [AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) implizit.

> [!NOTE]
>  Die Steuerelement-hosting-API bildet die Grundlage für ATLs-Unterstützung für ActiveX-Steuerelementcontainern. Es besteht jedoch in der Regel kaum Bedarf, diese Funktionen direkt aufzurufen, wenn Sie nutzen, oder ATLs-Wrapperklassen nutzen. Weitere Informationen finden Sie unter [der ATL-Klassen vereinfachen ActiveX-Steuerelementcontainern](which-atl-classes-facilitate-activex-control-containment-q.md).  

## <a name="what-is-atlaxwin100"></a>Was ist AtlAxWin100?

`AtlAxWin100` ist der Name einer Fenster-Klasse, die ATLs-steuerelementhostings Funktionalität bietet. Wenn Sie eine Instanz dieser Klasse erstellen, verwendet die Fensterprozedur automatisch die Steuerelement-hosting-API erstellen ein Objekt mit dem Fenster verknüpft ist, und laden, mit dem Steuerelement, das Sie als Titel des Fensters angeben. 

## <a name="when-do-i-need-to-call-atlaxwininit"></a>Wann muss ich AtlAxWinInit aufrufen?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) registriert die **"AtlAxWin80"** Fensterklasse (sowie eine Reihe von benutzerdefinierten fenstermeldungen), damit diese Funktion aufgerufen werden muss, bevor Sie versuchen, ein Hostfenster zu erstellen. Müssen Sie jedoch nicht immer diese Funktion explizit aufzurufen, da das hosting-APIs (und die Klassen, die sie verwenden) rufen Sie diese Funktion häufig für Sie. Es gibt keinen Schaden in diese Funktion mehr als einmal aufgerufen.

## <a name="what-is-a-host-object"></a>Was ist ein Hostobjekt?

Ein-Objekt ist ein COM-Objekt, den ActiveX-Steuerelementcontainer, die vom ATL für ein bestimmtes Fenster darstellt. Der Host Objekt Unterklassen der Fenster "Container", damit Nachrichten an das Steuerelement widerspiegeln, bietet die notwendigen Containerschnittstellen, die vom Steuerelement verwendet werden und macht die [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) und [ IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) Schnittstellen, die Ihnen ermöglichen, konfigurieren Sie die Umgebung des Steuerelements.

Sie können das Hostobjekt, das zum Festlegen der ambient-Eigenschaften des Containers verwenden.

## <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Kann ich mehr als ein Steuerelement in einem einzelnen Fenster hosten?

Es ist nicht möglich, mehr als ein Steuerelement in einem einzelnen Fenster der ATL-Host zu hosten. Jedes Hostfenster soll genau ein Steuerelement zu einem Zeitpunkt aufnehmen (Dies ermöglicht einen einfachen Mechanismus für die Verarbeitung der Nachricht Reflektion und pro-Control-ambient-Eigenschaften). Wenn Sie mehrere Steuerelemente in einem einzelnen Fenster finden Sie unter den Benutzer benötigen, ist es jedoch einfach, die mehrere Hostfenster als untergeordnete Elemente dieses Fensters zu erstellen.

## <a name="can-i-reuse-a-host-window"></a>Kann ich ein Hostfenster wiederverwenden?

Es wird nicht empfohlen, dass Sie Hostfenster wiederverwenden. Um die Stabilität des Codes zu gewährleisten, sollten Sie die Lebensdauer des Hostfensters an die Lebensdauer der ein einzelnes Steuerelement binden.

## <a name="when-do-i-need-to-call-atlaxwinterm"></a>Wann muss ich AtlAxWinInit aufrufen?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwinterm) hebt die Registrierung der **"AtlAxWin80"** Fensterklasse. Sie sollten diese Funktion aufrufen, (Wenn Sie sich nicht mehr benötigen, die zum Erstellen von Host-Windows), nachdem alle vorhandenen Hostfenster zerstört wurden. Wenn Sie diese Funktion nicht aufrufen, werden die Fensterklasse aufgehoben automatisch beim Beenden des Prozesses.

## <a name="hosting-activex-controls-using-atl-axhost"></a>Hosten von ActiveX-Steuerelementen mit ATL-xhost

Das Beispiel in diesem Abschnitt zeigt wie AXHost erstellen und Hosten ein ActiveX-Steuerelements, die verschiedene ATL-Funktionen verwenden. Darüber hinaus erfahren Sie, wie die Kontrolle und die Senke Ereignisse zugreifen (mit [IDispEventImpl](../atl/reference/idispeventimpl-class.md)) aus dem Steuerelement, das gehostet wird. Das Beispiel hostet das Kalender-Steuerelement in ein Hauptfenster oder in einem untergeordneten Fenster.

Beachten Sie, dass die Definition der `USE_METHOD` Symbol. Sie können den Wert dieses Symbols variiert zwischen 1 und 8 ändern. Der Wert des Symbols wird bestimmt, wie das Steuerelement erstellt wird:

- Für Werte des gerade `USE_METHOD`, der Aufruf zum Host Unterklassen eines Fensters erstellen und in einem Steuerelementhost konvertiert wird. Ungerade Werte erstellt der Code ein untergeordneten Fensters, das als Host fungiert.

- Für Werte des `USE_METHOD` zwischen 1 und 4, der Zugriff auf das Steuerelement und das Auffangen von Ereignissen werden erreicht, in der Aufruf, der auch auf den Host erstellt. Werte zwischen 5 und 8 den Host für die Schnittstellen Abfragen und verknüpfen Sie die Senke.

Hier finden Sie eine Zusammenfassung:

|USE_METHOD|Host|Steuern des Zugriffs und Auffangen|Gezeigt Funktion|
|-----------------|----------|--------------------------------------|---------------------------|
|1|Untergeordnete Fenster|Ein Schritt|CreateControlLicEx|
|2|Klicken Sie im Hauptfenster|Ein Schritt|AtlAxCreateControlLicEx|
|3|Untergeordnete Fenster|Ein Schritt|CreateControlEx|
|4|Klicken Sie im Hauptfenster|Ein Schritt|AtlAxCreateControlEx|
|5|Untergeordnete Fenster|Mehrere Schritte|CreateControlLic|
|6|Klicken Sie im Hauptfenster|Mehrere Schritte|AtlAxCreateControlLic|
|7|Untergeordnete Fenster|Mehrere Schritte|CreateControl|
|8|Klicken Sie im Hauptfenster|Mehrere Schritte|AtlAxCreateControl|

[!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Steuerelementkapselung – häufig gestellte Fragen](../atl/atl-control-containment-faq.md)<br/>
[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)<br/>
[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)<br/>
[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[CAxWindow2T-Klasse](../atl/reference/caxwindow2t-class.md)<br/>
[IAxWinHostWindowLic-Schnittstelle](../atl/reference/iaxwinhostwindowlic-interface.md)