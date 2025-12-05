// main.cpp
// Personal Productivity Dashboard
// Starter code skeleton for GitHub repository

#include <SFML/Graphics.hpp>
#include <SFML/Audio.hpp>
#include <iostream>

// -------------------------------
// Core Module Interfaces
// -------------------------------

class HabitLog {
public:
    void logHabit(const std::string& habitName) {
        std::cout << "Habit logged: " << habitName << std::endl;
        // Placeholder for persistence and observer notifications
    }
};

class AnalyticsModule {
public:
    void update() {
        std::cout << "Analytics updated." << std::endl;
    }
};

class SuggestionEngine {
public:
    void update() {
        std::cout << "Suggestions updated." << std::endl;
    }
};

class ChartView {
public:
    void update() {
        std::cout << "Chart view updated." << std::endl;
    }
};

class GamifiedEnvironment {
public:
    void update() {
        std::cout << "Gamified environment updated." << std::endl;
    }
};

// -------------------------------
// Application Entry Point
// -------------------------------

int main() {
    // Create SFML window
    sf::RenderWindow window(sf::VideoMode(800, 600), "Personal Productivity Dashboard");

    // Load font (placeholder)
    sf::Font font;
    if (!font.loadFromFile("assets/arial.ttf")) {
        std::cerr << "Failed to load font. Make sure assets/arial.ttf exists." << std::endl;
    }

    // Create a simple text label
    sf::Text title;
    title.setFont(font);
    title.setString("Personal Productivity Dashboard");
    title.setCharacterSize(24);
    title.setFillColor(sf::Color::Black);
    title.setPosition(100.f, 50.f);

    // Create modules
    HabitLog habitLog;
    AnalyticsModule analytics;
    SuggestionEngine suggestions;
    ChartView charts;
    GamifiedEnvironment gamified;

    // Main loop
    while (window.isOpen()) {
        sf::Event event;
        while (window.pollEvent(event)) {
            if (event.type == sf::Event::Closed)
                window.close();

            // Example: log habit on key press
            if (event.type == sf::Event::KeyPressed && event.key.code == sf::Keyboard::Space) {
                habitLog.logHabit("Exercise");
                analytics.update();
                suggestions.update();
                charts.update();
                gamified.update();
            }
        }

        // Clear and draw
        window.clear(sf::Color::White);

        // Draw placeholder UI
        window.draw(title);

        window.display();
    }

    return 0;
