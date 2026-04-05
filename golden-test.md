# 📘 Golden Tests (Flutter)

## 🔹 Overview  
Golden Tests in Flutter are used to test UI by comparing the current UI with a previously saved reference image (golden file).

It helps ensure that the UI design remains consistent over time.

## 🔹 Core Idea  
Current UI ➝ Compare with Golden Image ➝ Match / Fail

## 🔹 How It Works  

1. Create a widget UI  
2. Capture its screenshot (golden file)  
3. Run test → compare UI with saved image  
4. If UI changes → test fails  

## 🔹 Example
testWidgets('My Widget Golden Test', (tester) async {
  await tester.pumpWidget(MyWidget());

  await expectLater(
    find.byType(MyWidget),
    matchesGoldenFile('goldens/my_widget.png'),
  );
});

🔹 Use Cases
UI consistency testing
Design system validation
Prevent unwanted UI changes
Large-scale apps with many screens

🔹 Advantages
✔ Detects UI changes automatically
✔ Maintains design consistency
✔ Useful for team projects
✔ Saves manual testing time

🔹 Limitations
❌ Sensitive to small UI changes
❌ Needs proper setup
❌ Image management required

🔹 When to Use
Production apps
Apps with fixed design system
Reusable UI components

🔹 Conclusion
Golden Tests help ensure that your Flutter UI remains visually consistent by comparing it with a reference image, making UI testing more reliable and automated.