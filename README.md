# Professional-Dashboard-
// main.cpp
// Personal Productivity Dashboard
// Starter code skeleton for GitHub repository

#include <SFML/Graphics.hpp>
#include <SFML/Audio.hpp>
#include <iostream>

// Forward declarations of core modules
class HabitLog;
class AnalyticsModule;
class SuggestionEngine;
class ChartView;
class GamifiedEnvironment;

// -------------------------------
// Core Module Interfaces
// -------------------------------

class HabitLog {
public:
    void logHabit(const std::string& habitName) {
        std::cout << "Habit logged: " << habitName << std::endl;
        // TODO: Save to JSON persistence
        // TODO: Notify observers (Analytics, Suggestions, Charts, GamifiedEnv)
    }
};

class AnalyticsModule {
public:
    void update() {
        // TODO: Calculate streaks and trends
        std::cout << "Analytics updated." << std::endl;
    }
};

class SuggestionEngine {
public:
    void update() {
        // TODO: Generate motivational suggestions
        std::cout << "Suggestions updated." << std::endl;
    }
};

class ChartView {
public:
    void update() {
        // TODO: Render line/bar charts using SFML primitives
        std::cout << "Chart view updated." << std::endl;
    }
};

class GamifiedEnvironment {
public:
    void update() {
        // TODO: Unlock visuals based on milestones
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
        std::cerr << "Failed to load font." << std::endl;
    }

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

        // TODO: Draw UI components (menu, dashboard, charts, gamified scene)

        window.display();
    }

    return 0;
}
