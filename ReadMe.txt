Hier sind die verschiedenen Klassifikations-, Segmentierungs- und Datenerstellungsprogramme


1. Voronoi_train_data_LU:
	Erstellt Voronoi-Diagramme anhand von eingelesenen Bilder. Voreingestellt sollten jeweils 20 Voronoi-Zellen sein, die Klasse der Voronoi wird manuell durch einen Zufallsgenerator bestimmt. Durch die zugeordnete Zahl, zum Beispiel 1=spröde, 0=duktil kann und wird eine Maske erstellt, die zeigt, welche Klasse wo vorhanden ist. Als Ausgabe werden die Masken und Bilder ausgegeben, die gemäß ihrer Namen einander zugeordnet werden können.

2. VGG16_VGG19+RF
	Programm zur Klassifikation der Bruchflächen, basierend auf VGG backbone mit RF als Machine Learning Element. Das Programm ist darauf trainiert, dass einzelne Bildabschnitte (380x380)/(224x224), die durch das Wandernde Fenster erzeugt wurden den Referenzklassen spröde und duktil zugeorndet werden. Die erhaltene Ausgabe entspricht einem Sicherheitsmaß bei der Bewertung zu den Referenzzuständen

3. Code_Resnet_Semantic_Segmentation
	Programm zur Semantischen Segmentierung der Bruchflächen. Nach dem Einlesen der Trainingsdaten kann über einen learnrate-optimizer die bestmögliche Lernrate bestimmt werden, anschließend werden Bilder semantisch ausgewertet. Die Segmentierung wird direkt im Bild veranschaulicht, durch eine Überlagerung der Maske. Dabei werden die Grenzen der einzelnen Klassen als Linien eingezeichnet. Des Weiteren wurden diverse Filter etabliert, zum Einen das Glätten durch eine anpassbare Kernel-Size, zum Anderen ein Flughöhenfilter, der bei der momentanen Bildvergrößerung Einteilungen von unterhalb 1mm² herausfiltert. Abschließend wird das Ergebnis so ausgegeben, dass das Original+Linien, Sicherheitswerte und die diversen angepassten Filter angezeigt werden.
	Es wurden IoU-Werte von ca. 70% erreicht