import random


class ProjectIdeaGenerator:

    CATEGORIES = [
        "Web",
        "AIi",
        "Automation",
        "CLI",
        "Security",
        "Data Analysis",
        "Game",
        "Finance"
    ]

    FEATURES = [
        "User Authentication",
        "Dashboard",
        "REST API",
        "Report Generator",
        "Real-time Notifications",
        "File Processing",
        "Data Visualization",
        "Search Engine",
        "AI Assistant",
        "Analytics"
    ]

    TECHNOLOGIES = [
        "Python",
        "FastAPI",
        "Flask",
        "SQLite",
        "PostgreSQL",
        "Docker",
        "Redis",
        "Pandas"
    ]

    def generate(self):

        category = random.choice(self.CATEGORIES)

        feature_count = random.randint(2, 4)

        features = random.sample(
            self.FEATURES,
            feature_count
        )

        technologies = random.sample(
            self.TECHNOLOGIES,
            3
        )

        return {
            "category": category,
            "features": features,
            "technologies": technologies
        }

    def display(self):

        idea = self.generate()

        print("\n🚀 New Project Idea")
        print("=" * 40)

        print(
            f"Category: {idea['category']}"
        )

        print("\nFeatures:")

        for feature in idea["features"]:
            print(f"  • {feature}")

        print("\nTechnologies:")

        for tech in idea["technologies"]:
            print(f"  • {tech}")

        print("\nChallenge:")
        print(
            "Build it in less than 500 lines!"
        )


if __name__ == "__main__":

    generator = ProjectIdeaGenerator()

    while True:

        generator.display()

        again = input(
            "\nGenerate another? (y/n): "
        )

        if again.lower() != "y":
            break
