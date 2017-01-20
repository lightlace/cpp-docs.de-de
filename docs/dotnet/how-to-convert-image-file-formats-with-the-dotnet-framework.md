---
title: "Gewusst wie: Konvertieren von Bilddateiformaten mit .NET Framework"
ms.custom: na
ms.date: "12/08/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GDI+ [C++], Konvertieren von Bilddateiformaten"
  - "Grafik [C++], Konvertieren von Bilddateiformaten"
ms.assetid: 5d5384b0-b9b7-4262-b9ad-c4cb95f75ee4
caps.latest.revision: 13
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Konvertieren von Bilddateiformaten mit .NET Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<?xml version="1.0" encoding="utf-8"?>
\<developerHowToDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://clixdevr3.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>Die folgenden Codebeispiele zeigen die <codeEntityReference qualifyHint="true" autoUpgrade="true">T:System.Drawing.Image</codeEntityReference>-Klasse und die Enumeration <codeEntityReference qualifyHint="true" autoUpgrade="true">T:System.Drawing.Imaging.ImageFormat</codeEntityReference>, die zum Konvertieren und Speichern von Bilddateien verwendet wurden. Der folgende Code lädt ein Bild aus einer JPG-Datei und speichert es sowohl im Format GIF als auch im Format BMP. </para>
    <alert class="note">
      <para>GDI+ ist in Windows XP, Windows Server 2003 und Windows Vista enthalten und für Windows 2000 als verteilbare API erhältlich. Die neueste verteilbare Version können Sie unter <externalLink><linkText>http://go.microsoft.com/fwlink/?linkid=11232</linkText><linkUri>http://go.microsoft.com/fwlink/?linkid=11232</linkUri></externalLink> herunterladen. Weitere Informationen finden Sie unter \<legacyLink xlink:href="_gdiplus_GDI_start_cpp">GDI+</legacyLink>.</para>
    </alert>
  </introduction>
  <codeExample>
    <code>#using &lt;system.drawing.dll&gt;

using namespace System;
using namespace System::Drawing;
using namespace System::Drawing::Imaging;

int main()
{
   Image^ image = Image::FromFile("SampleImage.jpg");
   image-&gt;Save("SampleImage.png", ImageFormat::Png);
   image-&gt;Save("SampleImage.bmp", ImageFormat::Bmp);

   return 0;
}</code>
  </codeExample>
  <relatedTopics>
\<link xlink:href="2c7f3b0f-a266-4f0e-b318-d6f1371e04a9">.NET-Programmierung in C++</link>
<codeEntityReference autoUpgrade="true">N:System.Drawing</codeEntityReference>
</relatedTopics>
</developerHowToDocument>