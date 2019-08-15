---
title: GetProcAddress
ms.date: 11/04/2016
f1_keywords:
- GetProcAddress
helpviewer_keywords:
- DLLs [C++], GetProcAddress
- ordinal exports [C++]
- GetProcAddress method
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
ms.openlocfilehash: 2d322cfe7d3bd60d8d702a226e181eb7b4ede963
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493254"
---
# <a name="getprocaddress"></a>GetProcAddress

Prozesse, die explizit eine Verknüpfung mit einer DLL herstellen, rufen [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) auf, um die Adresse einer exportierten Funktion in der dll zu erhalten. Sie rufen die DLL-Funktion dann über den zurückgegebenen Funktionszeiger auf. **GetProcAddress** übernimmt als Parameter das dll-Modul handle (wird entweder von **LoadLibrary**, `AfxLoadLibrary`oder **GetModuleHandle**zurückgegeben) und übernimmt entweder den Namen der Funktion, die Sie aufrufen möchten, oder die Export Ordinalzahl der Funktion.

Da Sie die DLL-Funktion über einen Zeiger aufrufen und zur Kompilierungszeit keine Typüberprüfung erfolgt, sollten Sie sicherstellen, dass die Parameter für die Funktion korrekt sind, damit Sie nicht den auf dem Stapel belegten Speicherbereich überschreiten und eine Zugriffsverletzung verursachen. Eine Möglichkeit die Typsicherheit zu gewährleisten besteht darin, sich die Funktionsprototypen der exportierten Funktionen anzusehen und entsprechende Typdefinitionen für die Funktionszeiger zu erstellen. Beispiel:

```
typedef UINT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT);
...

HINSTANCE hDLL;               // Handle to DLL
LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer
DWORD dwParam1;
UINT  uParam2, uReturnVal;

hDLL = LoadLibrary("MyDLL");
if (hDLL != NULL)
{
   lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL,
                                           "DLLFunc1");
   if (!lpfnDllFunc1)
   {
      // handle the error
      FreeLibrary(hDLL);
      return SOME_ERROR_CODE;
   }
   else
   {
      // call the function
      uReturnVal = lpfnDllFunc1(dwParam1, uParam2);
   }
}
```

Wie Sie die gewünschte Funktion beim Aufrufen von **GetProcAddress** angeben, hängt davon ab, wie die dll erstellt wurde.

Sie können nur die Export Ordinalzahl abrufen, wenn die dll, mit der Sie Verknüpfungen erstellen, mit einer Modul Definitionsdatei (. def) erstellt wurde und die Ordinalzahlen mit den Funktionen im Abschnitt **Exports** der DEF-Datei der dll aufgelistet werden. Der Aufruf von **GetProcAddress** mit einer Export Ordinalzahl (im Gegensatz zum Funktionsnamen) ist etwas schneller, wenn die dll viele exportierte Funktionen hat, da die Export Ordinalzahlen als Indizes für die Export Tabelle der dll fungieren. Mit einer Export Ordinalzahl kann **GetProcAddress** die Funktion direkt finden, anstatt den angegebenen Namen mit den Funktionsnamen in der Export Tabelle der dll zu vergleichen. Allerdings sollten Sie **GetProcAddress** nur mit einer Export Ordinalzahl aufrufen, wenn Sie die Zuweisung der Ordinalzahlen zu den exportierten Funktionen in der DEF-Datei steuern können.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [LoadLibrary und AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary)

- [Exportieren aus einer DLL mithilfe von DEF-Dateien](exporting-from-a-dll-using-def-files.md)

## <a name="see-also"></a>Siehe auch

[Erstellen von C/C++-DLLs in Visual Studio](dlls-in-visual-cpp.md)
