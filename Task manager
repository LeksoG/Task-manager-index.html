<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tasklytic</title>
    <style>
        :root {
            /* Primary Colors */
            --primary: #4f46e5;
            --primary-dark: #4338ca;
            --primary-light: #818cf8;
            --primary-gradient: linear-gradient(135deg, #4f46e5 0%, #3b82f6 100%);
            
            /* Secondary Colors */
            --secondary: #0ea5e9;
            --secondary-dark: #0284c7;
            --secondary-light: #7dd3fc;
            
            /* Accent Colors */
            --accent: #f97316;
            --accent-dark: #ea580c;
            --accent-light: #fdba74;
            
            /* Status Colors */
            --success: #10b981;
            --success-light: #d1fae5;
            --warning: #f59e0b;
            --warning-light: #fef3c7;
            --danger: #ef4444;
            --danger-light: #fee2e2;
            
            /* Gray Scale */
            --gray-50: #f9fafb;
            --gray-100: #f3f4f6;
            --gray-200: #e5e7eb;
            --gray-300: #d1d5db;
            --gray-400: #9ca3af;
            --gray-500: #6b7280;
            --gray-600: #4b5563;
            --gray-700: #374151;
            --gray-800: #1f2937;
            --gray-900: #111827;
            
            /* Category Colors */
            --work-color: #4f46e5;
            --work-light: #e0e7ff;
            --personal-color: #8b5cf6;
            --personal-light: #ede9fe;
            --shopping-color: #06b6d4;
            --shopping-light: #cffafe;
            --health-color: #10b981;
            --health-light: #d1fae5;
            --finance-color: #f59e0b;
            --finance-light: #fef3c7;
            --education-color: #ef4444;
            --education-light: #fee2e2;
            
            /* Shadows */
            --card-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
            --card-shadow-hover: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
            --sidebar-shadow: 4px 0 10px -3px rgba(0, 0, 0, 0.1);

            /* Highlight Colors */
            --highlight-color: #ec4899;
            --highlight-light: #fce7f3;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            color: var(--gray-700);
            line-height: 1.7;
            background-color: var(--gray-50);
            min-height: 100vh;
            overflow-x: hidden;
            width: 100%;
        }

        /* Typography */
        h1, h2, h3, h4, h5, h6 {
            color: var(--gray-800);
            font-weight: 600;
            letter-spacing: -0.025em;
        }

        .container {
            width: 100%;
            max-width: 100%;
            margin: 0 auto;
            padding: 0 1rem;
        }

        /* Improved Welcome Animation with Typing Effect */
        .welcome-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: var(--gray-50);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            z-index: 2000;
            transition: opacity 0.5s ease, visibility 0.5s ease;
            overflow: hidden;
        }

        /* Ring animation container */
        .welcome-container {
            position: relative;
            width: 200px;
            height: 200px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* Task cards animation */
        .task-card {
            position: absolute;
            width: 60px;
            height: 60px;
            background: white;
            border-radius: 12px;
            box-shadow: var(--card-shadow);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: var(--primary);
            animation: float-animation 3s ease-in-out infinite;
            opacity: 0;
        }

        .task-card:nth-child(1) {
            background-color: var(--work-light);
            animation-delay: 0s;
            transform: translate(-80px, -80px);
        }

        .task-card:nth-child(2) {
            background-color: var(--personal-light);
            animation-delay: 0.7s;
            transform: translate(80px, -80px);
        }

        .task-card:nth-child(3) {
            background-color: var(--shopping-light);
            animation-delay: 1.4s;
            transform: translate(-80px, 80px);
        }

        .task-card:nth-child(4) {
            background-color: var(--health-light);
            animation-delay: 2.1s;
            transform: translate(80px, 80px);
        }

        @keyframes float-animation {
            0% {
                opacity: 0;
                transform: translate(var(--x, 0), var(--y, 0)) scale(0.5);
            }
            20% {
                opacity: 1;
                transform: translate(var(--x, 0), var(--y, 0)) scale(1);
            }
            80% {
                opacity: 1;
                transform: translate(var(--x, 0), var(--y, 0)) scale(1);
            }
            100% {
                opacity: 0;
                transform: translate(var(--x, 0), var(--y, 0)) scale(0.5);
            }
        }

        /* Typing animation for the app title */
        .app-title {
            position: relative;
            font-size: 3rem;
            font-weight: 700;
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-align: center;
            opacity: 0;
            animation: fade-in 0.5s ease 0.5s forwards;
            white-space: nowrap;
            overflow: hidden;
            border-right: 0.15em solid var(--primary);
            width: 0;
            animation: typing 2.5s steps(10, end) 0.5s forwards, 
                       blink-caret 0.75s step-end infinite;
        }

        @keyframes typing {
            from { width: 0; }
            to { width: 10ch; }
        }

        @keyframes blink-caret {
            from, to { border-color: transparent; }
            50% { border-color: var(--primary); }
        }

        @keyframes fade-in {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .exclamation {
            color: var(--accent);
            display: inline-block;
            transform-origin: bottom;
            animation: bounce 0.5s ease 3s;
        }

        @keyframes bounce {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-15px);
            }
        }

        /* App Container fade in effect */
        .app-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: var(--gray-50);
            z-index: 1500;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.8s ease, visibility 0.8s ease;
        }

        .app-container.visible {
            opacity: 1;
            visibility: visible;
        }

        /* Header */
        header {
            background: var(--primary-gradient);
            color: white;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
            padding: 0.75rem 0;
            transition: background 0.3s ease;
            width: 100%;
        }

        header .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
        }

        .logo {
            font-size: 1.75rem;
            font-weight: 700;
            color: white;
            display: flex;
            align-items: center;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
            letter-spacing: -0.5px;
        }

        .logo i {
            margin-right: 0.75rem;
            font-size: 2rem;
            background: white;
            color: var(--primary);
            width: 42px;
            height: 42px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 10px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .theme-toggle {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: none;
            width: 36px;
            height: 36px;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .theme-toggle:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-2px);
        }

        /* Main Content */
        .main-content {
            display: flex;
            margin-top: 1rem;
            gap: 2rem;
            height: calc(100vh - 90px);
            width: 100%;
            transition: all 0.3s ease-in-out;
        }

        /* Sidebar */
        .sidebar {
            width: 280px;
            min-width: 280px;
            background-color: white;
            border-radius: 12px;
            box-shadow: var(--sidebar-shadow);
            padding: 1.5rem 1rem;
            border: 1px solid var(--gray-200);
            position: sticky;
            top: 90px;
            height: calc(100vh - 120px);
            overflow-y: auto;
            transition: transform 0.4s ease, opacity 0.4s ease;
        }

        .sidebar-header {
            margin-bottom: 1.5rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid var(--gray-200);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .sidebar-header h3 {
            font-size: 1.25rem;
            color: var(--gray-800);
        }

        /* Improved Category Selection with Sliding Indicator */
        .categories-container {
            position: relative;
            overflow: hidden;
        }

        .category-slider {
            display: flex;
            flex-direction: column;
            position: relative;
        }

        /* Sliding Active Indicator */
        .active-category-indicator {
            position: absolute;
            left: 0;
            width: 100%;
            height: 58px; /* Match category height */
            background: var(--primary-gradient);
            border-radius: 10px;
            transition: transform 0.3s ease;
            z-index: 1;
            opacity: 0.9;
            pointer-events: none; /* Allow clicks to pass through */
        }

        .category {
            margin-bottom: 0.75rem;
            cursor: pointer;
            padding: 1rem;
            border-radius: 10px;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: space-between;
            color: var(--gray-700);
            font-weight: 500;
            position: relative;
            z-index: 2; /* Place above the indicator */
        }

        .category:hover:not(.active) {
            background-color: rgba(79, 70, 229, 0.1);
            transform: translateX(5px);
        }

        .category.active {
            color: white;
        }

        .category-label {
            display: flex;
            align-items: center;
        }

        .category i {
            margin-right: 0.75rem;
            font-size: 1.2rem;
            width: 24px;
            text-align: center;
        }

        .task-count {
            background-color: rgba(255, 255, 255, 0.3);
            color: inherit;
            font-size: 0.75rem;
            font-weight: 600;
            width: 24px;
            height: 24px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }

        .category:not(.active) .task-count {
            background-color: var(--gray-200);
            color: var(--gray-700);
        }

        /* Tasks Container */
        .tasks-container {
            flex: 1;
            display: flex;
            flex-direction: column;
            overflow: hidden;
            transition: opacity 0.4s ease;
        }

        .tasks-header {
            margin-bottom: 1.5rem;
            position: relative;
        }

        /* REDESIGNED SEARCH CONTAINER */
        .search-container {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 1.5rem;
            position: relative;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            z-index: 10;
        }

        .search-input {
            width: 100%;
            padding: 0.9rem 1rem 0.9rem 3rem;
            border: 1px solid var(--gray-300);
            border-radius: 30px;
            font-size: 1.1rem;
            background-color: white;
            box-shadow: var(--card-shadow);
            transition: all 0.3s ease;
        }

        .search-input:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(79, 70, 229, 0.2);
        }

        .search-icon {
            position: absolute;
            left: 1.2rem;
            top: 50%;
            transform: translateY(-50%);
            color: var(--gray-500);
            font-size: 1.2rem;
            z-index: 2;
        }

        /* Search Overlay */
        .search-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            backdrop-filter: blur(5px);
            z-index: 5;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s ease, visibility 0.3s ease;
        }

        .search-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        /* Search Suggestions */
        .search-suggestions {
            position: absolute;
            top: 100%;
            left: 0;
            width: 100%;
            background-color: white;
            border-radius: 12px;
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease, opacity 0.3s ease;
            opacity: 0;
            z-index: 20;
        }

        .search-suggestions.active {
            max-height: 300px;
            opacity: 1;
            overflow-y: auto;
            padding: 0.5rem 0;
        }

        .suggestion-item {
            padding: 1rem;
            display: flex;
            align-items: center;
            justify-content: space-between;
            transition: background-color 0.2s ease;
            cursor: pointer;
            border-left: 4px solid transparent;
        }

        .suggestion-item:hover {
            background-color: var(--gray-100);
        }

        .suggestion-content {
            flex: 1;
        }

        .suggestion-title {
            font-weight: 600;
            margin-bottom: 0.25rem;
        }

        .suggestion-category {
            font-size: 0.85rem;
            color: var(--gray-600);
            display: flex;
            align-items: center;
        }

        .suggestion-category i {
            margin-right: 0.25rem;
        }

        .suggestion-priority {
            padding: 0.25rem 0.5rem;
            border-radius: 30px;
            font-size: 0.75rem;
            font-weight: 600;
            margin-right: 0.5rem;
        }

        .priority-high {
            background-color: var(--danger-light);
            color: var(--danger);
        }

        .priority-medium {
            background-color: var(--warning-light);
            color: var(--warning);
        }

        .priority-low {
            background-color: var(--success-light);
            color: var(--success);
        }

        .suggestion-actions {
            display: flex;
            gap: 0.5rem;
        }

        .suggestion-action {
            width: 32px;
            height: 32px;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: var(--gray-100);
            transition: all 0.2s ease;
            color: var(--gray-600);
            font-size: 0.9rem;
            border: none;
            cursor: pointer;
        }

        .suggestion-action:hover {
            color: white;
            transform: translateY(-2px);
        }

        .suggestion-action.edit:hover {
            background-color: var(--secondary);
        }

        .suggestion-action.delete:hover {
            background-color: var(--danger);
        }

        /* End of SEARCH REDESIGN */

        .section-title {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid var(--gray-200);
        }

        .section-title h2 {
            font-size: 1.75rem;
            color: var(--gray-800);
            position: relative;
            padding-left: 1rem;
            display: flex;
            align-items: center;
        }

        .section-title h2::before {
            content: '';
            position: absolute;
            left: 0;
            top: 50%;
            transform: translateY(-50%);
            height: 70%;
            width: 6px;
            background: var(--primary-gradient);
            border-radius: 3px;
            transition: background 0.3s ease;
        }

        .section-title h2 i {
            margin-right: 0.75rem;
            font-size: 1.75rem;
        }

        .category-description {
            color: var(--gray-600);
            margin-top: 0.5rem;
            font-size: 1.1rem;
        }

        .task-filters {
            display: flex;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .filter-btn {
            background-color: white;
            border: 1px solid var(--gray-300);
            padding: 0.5rem 1rem;
            border-radius: 8px;
            font-size: 0.9rem;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s ease;
            color: var(--gray-700);
        }

        .filter-btn:hover {
            border-color: var(--primary);
            color: var(--primary);
        }

        .filter-btn.active {
            background-color: var(--primary);
            color: white;
            border-color: var(--primary);
        }

        .task-sort {
            display: flex;
            align-items: center;
            background-color: white;
            padding: 0.5rem 0.75rem;
            border-radius: 8px;
            box-shadow: var(--card-shadow);
            border: 1px solid var(--gray-200);
        }

        .sort-label {
            margin-right: 0.5rem;
            font-size: 0.9rem;
            color: var(--gray-600);
            font-weight: 500;
        }

        /* Button Styles */
        .btn {
            padding: 0.75rem 1.5rem;
            border-radius: 10px;
            border: none;
            cursor: pointer;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
            letter-spacing: -0.01em;
            font-size: 1rem;
        }

        .btn-icon {
            margin-right: 0.5rem;
            font-size: 1.1rem;
        }

        .btn-primary {
            background: var(--primary-gradient);
            color: white;
            box-shadow: 0 4px 6px -1px rgba(79, 70, 229, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 15px -3px rgba(79, 70, 229, 0.4);
        }

        .btn-primary:active {
            transform: translateY(1px);
        }

        .btn-secondary {
            background: var(--secondary-gradient);
            color: white;
            box-shadow: 0 4px 6px -1px rgba(14, 165, 233, 0.3);
        }

        .btn-secondary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 15px -3px rgba(14, 165, 233, 0.4);
        }

        .btn-danger {
            background-color: var(--danger);
            color: white;
        }

        .btn-danger:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 15px -3px rgba(239, 68, 68, 0.4);
        }

        .btn-cancel {
            background-color: var(--gray-200);
            color: var(--gray-700);
        }

        .btn-cancel:hover {
            background-color: var(--gray-300);
        }

        .btn-select {
            background-color: white;
            border: 1px solid var(--gray-300);
            padding: 0.5rem 2.5rem 0.5rem 1rem;
            border-radius: 8px;
            font-size: 0.95rem;
            appearance: none;
            cursor: pointer;
            background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' fill='%236b7280' viewBox='0 0 16 16'%3E%3Cpath d='M7.247 11.14 2.451 5.658C1.885 5.013 2.345 4 3.204 4h9.592a1 1 0 0 1 .753 1.659l-4.796 5.48a1 1 0 0 1-1.506 0z'/%3E%3C/svg%3E");
            background-repeat: no-repeat;
            background-position: calc(100% - 0.75rem) center;
            background-size: 14px;
            transition: all 0.3s ease;
        }

        .btn-select:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(79, 70, 229, 0.2);
        }

        /* Dashboard Section */
        .dashboard {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0;
            transform: translateY(20px);
            animation: fade-slide-up 0.6s ease-out forwards;
        }

        @keyframes fade-slide-up {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .stat-card {
            background-color: white;
            border-radius: 12px;
            padding: 1.5rem;
            box-shadow: var(--card-shadow);
            border: 1px solid var(--gray-200);
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--card-shadow-hover);
        }

        .stat-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 1rem;
        }

        .stat-title {
            font-size: 1.1rem;
            color: var(--gray-600);
            font-weight: 500;
        }

        .stat-icon {
            width: 40px;
            height: 40px;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: white;
        }

        .stat-icon.total {
            background-color: var(--primary);
        }

        .stat-icon.completed {
            background-color: var(--success);
        }

        .stat-icon.pending {
            background-color: var(--warning);
        }

        .stat-icon.overdue {
            background-color: var(--danger);
        }

        .stat-value {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--gray-800);
            margin-bottom: 0.5rem;
        }

        .stat-change {
            display: flex;
            align-items: center;
            font-size: 0.9rem;
            font-weight: 500;
        }

        .stat-change.positive {
            color: var(--success);
        }

        .stat-change.negative {
            color: var(--danger);
        }

        .stat-change i {
            margin-right: 0.25rem;
        }

        /* Task List */
        .task-list-wrapper {
            flex: 1;
            overflow-y: auto;
            padding-right: 0.5rem;
            opacity: 0;
            transform: translateY(20px);
            animation: fade-slide-up 0.6s ease-out 0.4s forwards;
        }

        .task-list {
            background-color: white;
            border-radius: 12px;
            box-shadow: var(--card-shadow);
            padding: 1.5rem;
            margin-bottom: 2rem;
            border: 1px solid var(--gray-200);
            min-height: 300px;
            transition: opacity 0.3s ease;
        }

        /* Enhanced Task Item Styles */
        .task-item {
            display: flex;
            align-items: center;
            padding: 1.25rem;
            border-radius: 10px;
            margin-bottom: 1rem;
            background-color: var(--gray-50);
            transition: all 0.3s ease;
            border: 1px solid var(--gray-200);
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            cursor: pointer;
            animation: fade-in 0.5s ease-out, slide-in 0.5s ease-out;
        }

        .task-item:hover {
            box-shadow: var(--card-shadow-hover);
            transform: translateY(-2px);
        }

        @keyframes slide-in {
            from { transform: translateX(-20px); }
            to { transform: translateX(0); }
        }

        /* Purple curtain highlight effect for searched tasks - MODIFIED to go from inside to outside */
        .task-item.search-highlight {
            position: relative;
            overflow: hidden;
            border-color: var(--primary);
            box-shadow: 0 0 0 2px rgba(79, 70, 229, 0.2);
            animation: search-highlight-border 3s ease forwards;
        }

        .task-item.search-highlight::before,
        .task-item.search-highlight::after {
            content: '';
            position: absolute;
            top: 0;
            height: 100%;
            width: 50%;
            background-color: rgba(79, 70, 229, 0.15);
            z-index: 1;
            animation: curtain-close 0.6s ease forwards, curtain-fade 2.4s ease 0.6s forwards;
        }

        .task-item.search-highlight::before {
            left: 0;
            transform-origin: left center;
        }

        .task-item.search-highlight::after {
            right: 0;
            transform-origin: right center;
        }

        @keyframes curtain-close {
            from { transform: scaleX(0); }
            to { transform: scaleX(1); }
        }

        @keyframes curtain-fade {
            0% { opacity: 1; }
            100% { opacity: 0; }
        }

        @keyframes search-highlight-border {
            0% { 
                border-color: var(--primary);
                box-shadow: 0 0 0 2px rgba(79, 70, 229, 0.2);
            }
            70% { 
                border-color: var(--primary);
                box-shadow: 0 0 0 2px rgba(79, 70, 229, 0.2);
            }
            100% { 
                border-color: var(--gray-200);
                box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
            }
        }

        .task-checkbox {
            margin-right: 1.25rem;
        }

        .task-checkbox input {
            appearance: none;
            width: 24px;
            height: 24px;
            border: 2px solid var(--gray-400);
            border-radius: 6px;
            position: relative;
            cursor: pointer;
            transition: all 0.2s ease;
        }

        .task-checkbox input:checked {
            background-color: var(--primary);
            border-color: var(--primary);
        }

        .task-checkbox input:checked::after {
            content: '✓';
            position: absolute;
            color: white;
            font-size: 16px;
            font-weight: bold;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        .task-content {
            flex: 1;
        }

        .task-title {
            font-weight: 600;
            margin-bottom: 0.25rem;
            color: var(--gray-800);
            transition: all 0.2s ease;
            font-size: 1.1rem;
        }

        .task-description {
            color: var(--gray-600);
            font-size: 0.95rem;
            margin-bottom: 0.75rem;
        }

        .completed .task-title {
            text-decoration: line-through;
            color: var(--gray-400);
        }

        .completed .task-description {
            color: var(--gray-400);
        }

        .task-meta {
            display: flex;
            font-size: 0.9rem;
            color: var(--gray-500);
            flex-wrap: wrap;
            gap: 0.75rem;
        }

        .task-category, .task-date {
            display: flex;
            align-items: center;
            padding: 0.3rem 0.75rem;
            background-color: white;
            border-radius: 6px;
            box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
        }

        .task-category i, .task-date i {
            margin-right: 0.35rem;
            font-size: 0.95rem;
        }

        .task-priority {
            padding: 0.3rem 0.75rem;
            border-radius: 6px;
            font-size: 0.8rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
        }

        .task-actions {
            display: flex;
            gap: 0.75rem;
        }

        .task-action-btn {
            width: 40px;
            height: 40px;
            background-color: white;
            border: 1px solid var(--gray-200);
            border-radius: 8px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--gray-600);
            transition: all 0.3s ease;
            box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
            font-size: 1.1rem;
            z-index: 2;
        }

        .task-action-btn:hover {
            background-color: var(--gray-100);
            color: var(--primary);
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            transform: translateY(-2px);
        }

        .task-action-btn.edit:hover {
            color: var(--secondary);
        }

        .task-action-btn.delete:hover {
            color: var(--danger);
        }

        /* Category-specific styling */
        .category-work .section-title h2::before {
            background: linear-gradient(135deg, var(--work-color) 0%, var(--work-color) 100%);
        }

        .category-personal .section-title h2::before {
            background: linear-gradient(135deg, var(--personal-color) 0%, var(--personal-color) 100%);
        }

        .category-shopping .section-title h2::before {
            background: linear-gradient(135deg, var(--shopping-color) 0%, var(--shopping-color) 100%);
        }

        .category-health .section-title h2::before {
            background: linear-gradient(135deg, var(--health-color) 0%, var(--health-color) 100%);
        }

        .category-finance .section-title h2::before {
            background: linear-gradient(135deg, var(--finance-color) 0%, var(--finance-color) 100%);
        }

        .category-education .section-title h2::before {
            background: linear-gradient(135deg, var(--education-color) 0%, var(--education-color) 100%);
        }

        /* Empty State */
        .empty-state {
            text-align: center;
            padding: 3rem 2rem;
            color: var(--gray-500);
            background-color: var(--gray-50);
            border-radius: 12px;
            border: 2px dashed var(--gray-300);
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .empty-state:hover {
            border-color: var(--primary);
            background-color: var(--gray-100);
            transform: translateY(-5px);
        }

        .empty-state i {
            font-size: 4.5rem;
            margin-bottom: 1.5rem;
            color: var(--gray-300);
            background: linear-gradient(135deg, var(--gray-300) 0%, var(--gray-400) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .empty-state h3 {
            font-size: 1.75rem;
            margin-bottom: 0.5rem;
            color: var(--gray-700);
        }

        .empty-state p {
            font-size: 1.1rem;
            color: var(--gray-500);
        }

        /* Category-specific empty states */
        .empty-state.work i {
            background: linear-gradient(135deg, var(--work-color) 0%, var(--work-color) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .empty-state.personal i {
            background: linear-gradient(135deg, var(--personal-color) 0%, var(--personal-color) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .empty-state.shopping i {
            background: linear-gradient(135deg, var(--shopping-color) 0%, var(--shopping-color) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .empty-state.health i {
            background: linear-gradient(135deg, var(--health-color) 0%, var(--health-color) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .empty-state.finance i {
            background: linear-gradient(135deg, var(--finance-color) 0%, var(--finance-color) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .empty-state.education i {
            background: linear-gradient(135deg, var(--education-color) 0%, var(--education-color) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Task Detail Modal */
        .task-detail-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(5px);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s ease;
        }

        .task-detail-modal.active {
            opacity: 1;
            visibility: visible;
        }

        .task-detail-content {
            background-color: white;
            border-radius: 16px;
            width: 90%;
            max-width: 650px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
            transform: translateY(-20px);
            transition: all 0.3s ease;
            overflow: hidden;
            max-height: 90vh;
            display: flex;
            flex-direction: column;
        }

        .task-detail-modal.active .task-detail-content {
            transform: translateY(0);
        }

        .task-detail-header {
            padding: 1.75rem;
            border-bottom: 1px solid var(--gray-200);
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: var(--primary-gradient);
            color: white;
        }

        .task-detail-title {
            font-size: 1.5rem;
            font-weight: 600;
            color: white;
        }

        .task-detail-close {
            background: white;
            border: none;
            width: 36px;
            height: 36px;
            border-radius: 8px;
            font-size: 1.1rem;
            cursor: pointer;
            color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }

        .task-detail-close:hover {
            background-color: rgba(255, 255, 255, 0.9);
            transform: rotate(90deg);
        }

        .task-detail-body {
            padding: 1.75rem;
            overflow-y: auto;
        }

        .task-detail-meta {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .task-detail-badge {
            display: flex;
            align-items: center;
            padding: 0.5rem 1rem;
            border-radius: 30px;
            font-size: 0.9rem;
            font-weight: 500;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
        }

        .task-detail-badge i {
            margin-right: 0.5rem;
        }

        .task-detail-badge.category {
            background-color: var(--primary-light);
            color: var(--primary-dark);
        }

        .task-detail-badge.category.work {
            background-color: var(--work-light);
            color: var(--work-color);
        }

        .task-detail-badge.category.personal {
            background-color: var(--personal-light);
            color: var(--personal-color);
        }

        .task-detail-badge.category.shopping {
            background-color: var(--shopping-light);
            color: var(--shopping-color);
        }

        .task-detail-badge.category.health {
            background-color: var(--health-light);
            color: var(--health-color);
        }

        .task-detail-badge.category.finance {
            background-color: var(--finance-light);
            color: var(--finance-color);
        }

        .task-detail-badge.category.education {
            background-color: var(--education-light);
            color: var(--education-color);
        }

        .task-detail-badge.priority {
            background-color: var(--success-light);
            color: var(--success);
        }

        .task-detail-badge.priority.medium {
            background-color: var(--warning-light);
            color: var(--warning);
        }

        .task-detail-badge.priority.high {
            background-color: var(--danger-light);
            color: var(--danger);
        }

        .task-detail-badge.date {
            background-color: var(--gray-100);
            color: var(--gray-700);
        }

        .task-detail-badge.status {
            background-color: var(--success-light);
            color: var(--success);
        }

        .task-detail-badge.status.pending {
            background-color: var(--warning-light);
            color: var(--warning);
        }

        .task-detail-description {
            background-color: var(--gray-50);
            padding: 1.5rem;
            border-radius: 12px;
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
            line-height: 1.8;
            color: var(--gray-700);
        }

        .task-detail-actions {
            display: flex;
            justify-content: flex-end;
            gap: 1rem;
        }

        /* Modal Styles */
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            backdrop-filter: blur(5px);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s ease;
        }

        .modal.active {
            opacity: 1;
            visibility: visible;
        }

        .modal-content {
            background-color: white;
            border-radius: 16px;
            width: 90%;
            max-width: 650px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
            transform: translateY(-20px);
            transition: all 0.3s ease;
            overflow: hidden;
            max-height: 90vh;
            display: flex;
            flex-direction: column;
        }

        .modal.active .modal-content {
            transform: translateY(0);
        }

        .modal-header {
            padding: 1.75rem;
            border-bottom: 1px solid var(--gray-200);
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: var(--primary-gradient);
            color: white;
        }

        /* Category-specific modal headers */
        .modal-header.work {
            background: linear-gradient(135deg, var(--work-color) 0%, var(--work-color) 80%);
        }

        .modal-header.personal {
            background: linear-gradient(135deg, var(--personal-color) 0%, var(--personal-color) 80%);
        }

        .modal-header.shopping {
            background: linear-gradient(135deg, var(--shopping-color) 0%, var(--shopping-color) 80%);
        }

        .modal-header.health {
            background: linear-gradient(135deg, var(--health-color) 0%, var(--health-color) 80%);
        }

        .modal-header.finance {
            background: linear-gradient(135deg, var(--finance-color) 0%, var(--finance-color) 80%);
        }

        .modal-header.education {
            background: linear-gradient(135deg, var(--education-color) 0%, var(--education-color) 80%);
        }

        .modal-title {
            font-size: 1.5rem;
            font-weight: 600;
            color: white;
        }

        .modal-close {
            background: white;
            border: none;
            width: 36px;
            height: 36px;
            border-radius: 8px;
            font-size: 1.1rem;
            cursor: pointer;
            color: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }

        .modal-close:hover {
            background-color: rgba(255, 255, 255, 0.9);
            transform: rotate(90deg);
        }

        .modal-body {
            padding: 1.75rem;
            overflow-y: auto;
        }

        /* Confirm Delete Modal */
        .delete-modal .modal-header {
            background: linear-gradient(135deg, var(--danger) 0%, #ff6b6b 100%);
        }

        .delete-modal .modal-close {
            color: var(--danger);
        }

        .delete-icon {
            font-size: 4rem;
            color: var(--danger);
            margin-bottom: 1.5rem;
            text-align: center;
            display: block;
        }

        .delete-message {
            text-align: center;
            margin-bottom: 2rem;
            font-size: 1.1rem;
            color: var(--gray-700);
        }

        .delete-message strong {
            color: var(--gray-900);
            display: block;
            font-size: 1.2rem;
            margin-top: 0.5rem;
        }

        /* Form Styles */
        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: var(--gray-700);
            font-size: 1.05rem;
        }

        .form-control {
            width: 100%;
            padding: 0.9rem 1rem;
            border: 1px solid var(--gray-300);
            border-radius: 8px;
            font-size: 1.05rem;
            transition: all 0.3s ease;
            background-color: var(--gray-50);
        }

        .form-control:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(79, 70, 229, 0.2);
            background-color: white;
        }

        .form-error {
            color: var(--danger);
            font-size: 0.9rem;
            margin-top: 0.5rem;
            display: none;
        }

        .input-group {
            position: relative;
        }

        .input-icon {
            position: absolute;
            left: 1rem;
            top: 50%;
            transform: translateY(-50%);
            color: var(--gray-500);
            font-size: 1.1rem;
        }

        .input-with-icon {
            padding-left: 2.75rem;
        }

        .form-actions {
            display: flex;
            justify-content: flex-end;
            gap: 1rem;
            margin-top: 2rem;
        }

        /* Priority selector */
        .priority-selector {
            display: flex;
            gap: 1rem;
            margin-top: 0.5rem;
        }

        .priority-option {
            flex: 1;
            padding: 0.9rem;
            text-align: center;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 500;
            border: 2px solid var(--gray-200);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            font-size: 1.05rem;
        }

        .priority-option:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
        }

        .priority-option input {
            position: absolute;
            opacity: 0;
            width: 0;
            height: 0;
        }

        .priority-option.low {
            color: var(--success);
        }

        .priority-option.medium {
            color: var(--warning);
        }

        .priority-option.high {
            color: var(--danger);
        }

        .priority-option.low.selected {
            background-color: var(--success-light);
            border-color: var(--success);
        }

        .priority-option.medium.selected {
            background-color: var(--warning-light);
            border-color: var(--warning);
        }

        .priority-option.high.selected {
            background-color: var(--danger-light);
            border-color: var(--danger);
        }

        .priority-option i {
            margin-right: 0.5rem;
        }

        /* Category selector */
        .category-selector {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1rem;
            margin-top: 0.5rem;
        }

        .category-option {
            padding: 1rem;
            text-align: center;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 500;
            border: 2px solid var(--gray-200);
            transition: all 0.3s ease;
            color: var(--gray-700);
            position: relative;
            font-size: 1rem;
        }

        .category-option:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
        }

        .category-option input {
            position: absolute;
            opacity: 0;
            width: 0;
            height: 0;
        }

        .category-option.selected {
            background-color: var(--primary-light);
            border-color: var(--primary);
            color: var(--primary-dark);
        }

        .category-option.work.selected {
            background-color: var(--work-light);
            border-color: var(--work-color);
            color: var(--work-color);
        }

        .category-option.personal.selected {
            background-color: var(--personal-light);
            border-color: var(--personal-color);
            color: var(--personal-color);
        }

        .category-option.shopping.selected {
            background-color: var(--shopping-light);
            border-color: var(--shopping-color);
            color: var(--shopping-color);
        }

        .category-option.health.selected {
            background-color: var(--health-light);
            border-color: var(--health-color);
            color: var(--health-color);
        }

        .category-option.finance.selected {
            background-color: var(--finance-light);
            border-color: var(--finance-color);
            color: var(--finance-color);
        }

        .category-option.education.selected {
            background-color: var(--education-light);
            border-color: var(--education-color);
            color: var(--education-color);
        }

        .category-option i {
            display: block;
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
        }

        /* Category container transitions */
        .category-container {
            transition: opacity 0.3s ease;
            width: 100%;
        }
        
        .category-container.fade-out {
            opacity: 0;
        }
        
        .category-container.fade-in {
            opacity: 0;
            animation: fade-in 0.3s ease forwards;
        }

        /* Category-specific background styles */
        .task-list.work {
            border-left: 4px solid var(--work-color);
            background-color: rgba(224, 231, 255, 0.3);
        }

        .task-list.personal {
            border-left: 4px solid var(--personal-color);
            background-color: rgba(237, 233, 254, 0.3);
        }

        .task-list.shopping {
            border-left: 4px solid var(--shopping-color);
            background-color: rgba(207, 250, 254, 0.3);
        }

        .task-list.health {
            border-left: 4px solid var(--health-color);
            background-color: rgba(209, 250, 229, 0.3);
        }

        .task-list.finance {
            border-left: 4px solid var(--finance-color);
            background-color: rgba(254, 243, 199, 0.3);
        }

        .task-list.education {
            border-left: 4px solid var(--education-color);
            background-color: rgba(254, 226, 226, 0.3);
        }

        /* Notification System */
        .notification-container {
            position: fixed;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 1500;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
        }

        .notification {
            padding: 1rem 1.5rem;
            border-radius: 10px;
            background-color: white;
            color: var(--gray-800);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
            font-weight: 500;
            display: flex;
            align-items: center;
            transform: translateY(100px);
            opacity: 0;
            transition: transform 0.3s ease, opacity 0.3s ease;
            max-width: 400px;
            width: 100%;
        }

        .notification.show {
            transform: translateY(0);
            opacity: 1;
        }

        .notification-icon {
            margin-right: 0.75rem;
            font-size: 1.25rem;
        }

        .notification.success {
            background-color: var(--success-light);
            color: var(--success);
            border-left: 4px solid var(--success);
        }

        .notification.warning {
            background-color: var(--warning-light);
            color: var(--warning);
            border-left: 4px solid var(--warning);
        }

        .notification.error {
            background-color: var(--danger-light);
            color: var(--danger);
            border-left: 4px solid var(--danger);
        }

        .notification.info {
            background-color: var(--secondary-light);
            color: var(--secondary);
            border-left: 4px solid var(--secondary);
        }

        /* Mobile styles */
        @media (max-width: 1200px) {
            .dashboard {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 992px) {
            .logo span {
                display: block;
            }
            
            .main-content {
                flex-direction: column;
                height: auto;
            }

            .sidebar {
                width: 100%;
                height: auto;
                max-height: 300px;
                margin-bottom: 1.5rem;
                overflow-y: auto;
            }
            
            .tasks-container {
                height: auto;
            }
        }

        @media (max-width: 768px) {
            .main-content {
                flex-direction: column;
            }

            .sidebar {
                width: 100%;
                position: relative;
                top: 0;
                height: auto;
                max-height: none;
                border-radius: 12px;
            }

            .task-item {
                flex-direction: column;
                align-items: flex-start;
                padding: 1.25rem;
            }

            .task-content {
                width: 100%;
                margin-bottom: 1rem;
            }

            .task-meta {
                margin-bottom: 1rem;
            }

            .task-actions {
                width: 100%;
                justify-content: flex-end;
            }

            .dashboard {
                grid-template-columns: 1fr;
            }

            .category-selector {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        /* Dark Mode Styles */
        body.dark-mode {
            background-color: var(--gray-900);
            color: var(--gray-300);
        }

        body.dark-mode h1, 
        body.dark-mode h2, 
        body.dark-mode h3, 
        body.dark-mode h4, 
        body.dark-mode h5, 
        body.dark-mode h6 {
            color: white;
        }

        body.dark-mode .sidebar,
        body.dark-mode .task-list,
        body.dark-mode .stat-card,
        body.dark-mode .modal-content,
        body.dark-mode .task-sort,
        body.dark-mode .search-suggestions,
        body.dark-mode .task-detail-content {
            background-color: var(--gray-800);
            border-color: var(--gray-700);
        }

        body.dark-mode .task-detail-description {
            background-color: var(--gray-900);
        }

        body.dark-mode .suggestion-item:hover {
            background-color: var(--gray-700);
        }

        body.dark-mode .task-item {
            background-color: var(--gray-900);
            border-color: var(--gray-700);
        }

        body.dark-mode .task-item.search-highlight {
            border-color: var(--primary-light);
            box-shadow: 0 0 0 2px rgba(129, 140, 248, 0.2);
        }

        body.dark-mode .task-item.search-highlight::before,
        body.dark-mode .task-item.search-highlight::after {
            background-color: rgba(129, 140, 248, 0.2);
        }

        /* Improved sidebar text visibility in dark mode */
        body.dark-mode .category:not(.active) {
            color: var(--gray-200);
        }

        body.dark-mode .category:hover:not(.active) {
            background-color: rgba(129, 140, 248, 0.2);
            color: white;
        }

        body.dark-mode .search-input,
        body.dark-mode .form-control,
        body.dark-mode .form-select {
            background-color: var(--gray-700);
            border-color: var(--gray-600);
            color: var(--gray-200);
        }

        body.dark-mode .search-input:focus,
        body.dark-mode .form-control:focus,
        body.dark-mode .form-select:focus {
            background-color: var(--gray-800);
        }

        body.dark-mode .form-label {
            color: var(--gray-300);
        }

        body.dark-mode .empty-state {
            background-color: var(--gray-800);
            border-color: var(--gray-700);
            color: var(--gray-400);
        }

        body.dark-mode .empty-state:hover {
            border-color: var(--primary-light);
            background-color: var(--gray-700);
        }

        body.dark-mode .stat-value {
            color: white;
        }

        body.dark-mode .welcome-overlay {
            background-color: var(--gray-900);
        }

        body.dark-mode .app-container {
            background-color: var(--gray-900);
        }

        body.dark-mode .suggestion-action {
            background-color: var(--gray-700);
        }

        /* Category-specific backgrounds in dark mode */
        body.dark-mode .task-list.work {
            background-color: rgba(79, 70, 229, 0.1);
        }

        body.dark-mode .task-list.personal {
            background-color: rgba(139, 92, 246, 0.1);
        }

        body.dark-mode .task-list.shopping {
            background-color: rgba(6, 182, 212, 0.1);
        }

        body.dark-mode .task-list.health {
            background-color: rgba(16, 185, 129, 0.1);
        }

        body.dark-mode .task-list.finance {
            background-color: rgba(245, 158, 11, 0.1);
        }

        body.dark-mode .task-list.education {
            background-color: rgba(239, 68, 68, 0.1);
        }
    </style>
    <!-- Font Awesome CDN -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts - Poppins -->
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap">
</head>
<body>
    <!-- Welcome Animation Overlay with Typing Effect -->
    <div class="welcome-overlay" id="welcomeOverlay">
        <div class="welcome-container">
            <div class="task-card">
                <i class="fas fa-briefcase"></i>
            </div>
            <div class="task-card">
                <i class="fas fa-user"></i>
            </div>
            <div class="task-card">
                <i class="fas fa-shopping-cart"></i>
            </div>
            <div class="task-card">
                <i class="fas fa-heartbeat"></i>
            </div>
        </div>
        <div class="app-title">
            Tasklytic<span class="exclamation">!</span>
        </div>
    </div>

    <!-- App Container -->
    <div class="app-container" id="appContainer">
        <header>
            <div class="container">
                <div class="logo">
                    <i class="fas fa-tasks"></i>
                    <span>Tasklytic</span>
                </div>
                <div class="header-actions">
                    <button class="theme-toggle" id="themeToggle" aria-label="Toggle Theme">
                        <i class="fas fa-moon"></i>
                    </button>
                </div>
            </div>
        </header>

        <div class="container">
            <div class="main-content">
                <aside class="sidebar" id="sidebar">
                    <div class="sidebar-header">
                        <h3>Categories</h3>
                    </div>
                    <div class="categories-container">
                        <!-- Active Category Indicator (Sliding Highlight) -->
                        <div class="active-category-indicator" id="activeCategoryIndicator"></div>
                        
                        <div class="category-slider" id="categorySlider">
                            <div class="category active" data-category="all" role="button" tabindex="0">
                                <div class="category-label">
                                    <i class="fas fa-layer-group"></i>
                                    All Tasks
                                </div>
                                <div class="task-count">0</div>
                            </div>
                            <div class="category" data-category="work" role="button" tabindex="0">
                                <div class="category-label">
                                    <i class="fas fa-briefcase"></i>
                                    Work
                                </div>
                                <div class="task-count">0</div>
                            </div>
                            <div class="category" data-category="personal" role="button" tabindex="0">
                                <div class="category-label">
                                    <i class="fas fa-user"></i>
                                    Personal
                                </div>
                                <div class="task-count">0</div>
                            </div>
                            <div class="category" data-category="shopping" role="button" tabindex="0">
                                <div class="category-label">
                                    <i class="fas fa-shopping-cart"></i>
                                    Shopping
                                </div>
                                <div class="task-count">0</div>
                            </div>
                            <div class="category" data-category="health" role="button" tabindex="0">
                                <div class="category-label">
                                    <i class="fas fa-heartbeat"></i>
                                    Health
                                </div>
                                <div class="task-count">0</div>
                            </div>
                            <div class="category" data-category="finance" role="button" tabindex="0">
                                <div class="category-label">
                                    <i class="fas fa-dollar-sign"></i>
                                    Finance
                                </div>
                                <div class="task-count">0</div>
                            </div>
                            <div class="category" data-category="education" role="button" tabindex="0">
                                <div class="category-label">
                                    <i class="fas fa-graduation-cap"></i>
                                    Education
                                </div>
                                <div class="task-count">0</div>
                            </div>
                        </div>
                    </div>
                </aside>

                <div class="tasks-container">
                    <div class="tasks-header">
                        <!-- Redesigned Search Container -->
                        <div class="search-container">
                            <i class="fas fa-search search-icon" aria-hidden="true"></i>
                            <input type="text" class="search-input" id="searchInput" placeholder="Search tasks..." aria-label="Search tasks">
                            <div class="search-suggestions" id="searchSuggestions"></div>
                        </div>
                        <div class="search-overlay" id="searchOverlay"></div>
                        
                        <div class="category-container" id="categoryContainer">
                            <div class="section-title">
                                <div>
                                    <h2 id="currentCategory"><i class="fas fa-layer-group"></i> All Tasks</h2>
                                    <p class="category-description" id="categoryDescription">View and manage all your tasks in one place.</p>
                                </div>
                                <div class="section-actions">
                                    <div class="task-sort">
                                        <span class="sort-label">Sort by:</span>
                                        <select id="sortSelect" class="btn-select" aria-label="Sort tasks">
                                            <option value="date">Due Date</option>
                                            <option value="priority">Priority</option>
                                            <option value="name">Name</option>
                                        </select>
                                    </div>
                                </div>
                                <button class="btn btn-primary" id="addTaskBtn" aria-label="Add New Task">
                                    <i class="fas fa-plus btn-icon" aria-hidden="true"></i> Add Task
                                </button>
                            </div>
                        </div>
                    </div>

                    <!-- Dashboard Section - Only shown for "all" category -->
                    <div class="dashboard" id="dashboard">
                        <div class="stat-card">
                            <div class="stat-header">
                                <div class="stat-title">Total Tasks</div>
                                <div class="stat-icon total"><i class="fas fa-tasks"></i></div>
                            </div>
                            <div class="stat-value" id="totalTasksValue">0</div>
                            <div class="stat-change positive">
                                <i class="fas fa-arrow-up"></i> 5% from last week
                            </div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-header">
                                <div class="stat-title">Completed Tasks</div>
                                <div class="stat-icon completed"><i class="fas fa-check-circle"></i></div>
                            </div>
                            <div class="stat-value" id="completedTasksValue">0</div>
                            <div class="stat-change positive">
                                <i class="fas fa-arrow-up"></i> 12% from last week
                            </div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-header">
                                <div class="stat-title">Pending Tasks</div>
                                <div class="stat-icon pending"><i class="fas fa-clock"></i></div>
                            </div>
                            <div class="stat-value" id="pendingTasksValue">0</div>
                            <div class="stat-change negative">
                                <i class="fas fa-arrow-down"></i> 3% from last week
                            </div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-header">
                                <div class="stat-title">Overdue Tasks</div>
                                <div class="stat-icon overdue"><i class="fas fa-exclamation-circle"></i></div>
                            </div>
                            <div class="stat-value" id="overdueTasksValue">0</div>
                            <div class="stat-change negative">
                                <i class="fas fa-arrow-down"></i> 8% from last week
                            </div>
                        </div>
                    </div>

                    <!-- Filter buttons -->
                    <div class="task-filters" id="taskFilters">
                        <button class="filter-btn active" data-filter="all">All</button>
                        <button class="filter-btn" data-filter="pending">Pending</button>
                        <button class="filter-btn" data-filter="completed">Completed</button>
                        <button class="filter-btn" data-filter="overdue">Overdue</button>
                        <button class="filter-btn" data-filter="today">Due Today</button>
                    </div>

                    <div class="task-list-wrapper" id="taskListWrapper">
                        <div class="task-list" id="taskList" aria-live="polite">
                            <!-- Tasks will be populated here by JavaScript -->
                            <div class="empty-state" id="emptyState">
                                <i class="fas fa-clipboard-list" aria-hidden="true"></i>
                                <h3>No tasks yet</h3>
                                <p>Add your first task to get started</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Task Detail View Modal -->
        <div class="task-detail-modal" id="taskDetailModal" aria-modal="true" role="dialog">
            <div class="task-detail-content">
                <div class="task-detail-header">
                    <h3 class="task-detail-title" id="detailTitle">Task Details</h3>
                    <button class="task-detail-close" id="detailClose" aria-label="Close details">
                        <i class="fas fa-times" aria-hidden="true"></i>
                    </button>
                </div>
                <div class="task-detail-body">
                    <div class="task-detail-meta" id="detailMeta">
                        <!-- Meta information will be inserted here -->
                    </div>
                    <div class="task-detail-description" id="detailDescription">
                        <!-- Task description will be inserted here -->
                    </div>
                    <div class="task-detail-actions">
                        <button class="btn btn-primary" id="detailEditBtn">
                            <i class="fas fa-pencil-alt btn-icon" aria-hidden="true"></i> Edit Task
                        </button>
                    </div>
                </div>
            </div>
        </div>

        <!-- Add/Edit Task Modal -->
        <div class="modal" id="taskModal" aria-modal="true" role="dialog">
            <div class="modal-content">
                <div class="modal-header" id="modalHeader">
                    <h3 class="modal-title" id="modalTitle">Add New Task</h3>
                    <button class="modal-close" id="modalClose" aria-label="Close modal">
                        <i class="fas fa-times" aria-hidden="true"></i>
                    </button>
                </div>
                <div class="modal-body">
                    <form id="taskForm">
                        <input type="hidden" id="taskId">
                        <div class="form-group">
                            <label for="taskTitle" class="form-label">Task Title</label>
                            <div class="input-group">
                                <i class="fas fa-tasks input-icon" aria-hidden="true"></i>
                                <input type="text" id="taskTitle" class="form-control input-with-icon" placeholder="What needs to be done?" required aria-required="true">
                            </div>
                            <div class="form-error" id="titleError">Please enter a task title</div>
                        </div>
                        
                        <div class="form-group">
                            <label for="taskDescription" class="form-label">Description (Optional)</label>
                            <div class="input-group">
                                <i class="fas fa-align-left input-icon" aria-hidden="true"></i>
                                <textarea id="taskDescription" class="form-control input-with-icon" rows="3" placeholder="Add details about your task"></textarea>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label">Category</label>
                            <div class="category-selector">
                                <label class="category-option work" data-value="work">
                                    <input type="radio" name="category" value="work">
                                    <i class="fas fa-briefcase" aria-hidden="true"></i>
                                    Work
                                </label>
                                <label class="category-option personal" data-value="personal">
                                    <input type="radio" name="category" value="personal">
                                    <i class="fas fa-user" aria-hidden="true"></i>
                                    Personal
                                </label>
                                <label class="category-option shopping" data-value="shopping">
                                    <input type="radio" name="category" value="shopping">
                                    <i class="fas fa-shopping-cart" aria-hidden="true"></i>
                                    Shopping
                                </label>
                                <label class="category-option health" data-value="health">
                                    <input type="radio" name="category" value="health">
                                    <i class="fas fa-heartbeat" aria-hidden="true"></i>
                                    Health
                                </label>
                                <label class="category-option finance" data-value="finance">
                                    <input type="radio" name="category" value="finance">
                                    <i class="fas fa-dollar-sign" aria-hidden="true"></i>
                                    Finance
                                </label>
                                <label class="category-option education" data-value="education">
                                    <input type="radio" name="category" value="education">
                                    <i class="fas fa-graduation-cap" aria-hidden="true"></i>
                                    Education
                                </label>
                            </div>
                            <input type="hidden" id="taskCategory" value="work">
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label">Priority</label>
                            <div class="priority-selector">
                                <label class="priority-option low" data-value="low">
                                    <input type="radio" name="priority" value="low">
                                    <i class="fas fa-flag" aria-hidden="true"></i> Low
                                </label>
                                <label class="priority-option medium" data-value="medium">
                                    <input type="radio" name="priority" value="medium">
                                    <i class="fas fa-flag" aria-hidden="true"></i> Medium
                                </label>
                                <label class="priority-option high" data-value="high">
                                    <input type="radio" name="priority" value="high">
                                    <i class="fas fa-flag" aria-hidden="true"></i> High
                                </label>
                            </div>
                            <input type="hidden" id="taskPriority" value="low">
                        </div>
                        
                        <div class="form-group">
                            <label for="taskDueDate" class="form-label">Due Date</label>
                            <div class="input-group">
                                <i class="far fa-calendar-alt input-icon" aria-hidden="true"></i>
                                <input type="date" id="taskDueDate" class="form-control input-with-icon" required aria-required="true">
                            </div>
                            <div class="form-error" id="dateError">Please select a valid date</div>
                        </div>
                        
                        <div class="form-actions">
                            <button type="button" class="btn btn-cancel" id="cancelBtn">Cancel</button>
                            <button type="submit" class="btn btn-primary" id="saveTaskBtn">
                                <i class="fas fa-save btn-icon" aria-hidden="true"></i> Save Task
                            </button>
                        </div>
                    </form>
                </div>
            </div>
        </div>

        <!-- Confirmation Delete Modal -->
        <div class="modal delete-modal" id="deleteModal" aria-modal="true" role="dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h3 class="modal-title">Delete Task</h3>
                    <button class="modal-close" id="deleteModalClose" aria-label="Close modal">
                        <i class="fas fa-times" aria-hidden="true"></i>
                    </button>
                </div>
                <div class="modal-body">
                    <i class="fas fa-exclamation-triangle delete-icon" aria-hidden="true"></i>
                    <div class="delete-message">
                        Are you sure you want to delete this task?
                        <strong id="deleteTaskTitle"></strong>
                        This action cannot be undone.
                    </div>
                    <div class="form-actions">
                        <button type="button" class="btn btn-cancel" id="cancelDeleteBtn">Cancel</button>
                        <button type="button" class="btn btn-danger" id="confirmDeleteBtn">
                            <i class="fas fa-trash btn-icon" aria-hidden="true"></i> Delete
                        </button>
                    </div>
                </div>
            </div>
        </div>

        <!-- Notification Container -->
        <div class="notification-container" id="notificationContainer"></div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
    // App State 
    const AppState = (function() {
        // Always return an authenticated user
        let currentUser = {
            id: 'default-user',
            username: 'User',
            email: 'user@example.com'
        };
        
        const getCurrentUser = () => {
            return currentUser;
        };
        
        return {
            getCurrentUser
        };
    })();
    
    // UI Controller - Improved for smooth transitions
    const UIController = (function() {
        const welcomeOverlay = document.getElementById('welcomeOverlay');
        const appContainer = document.getElementById('appContainer');
        const themeToggle = document.getElementById('themeToggle');
        
        // Show welcome animation with smooth transition to the app
        const showWelcomeAnimation = () => {
            // Force the overlay to be visible initially
            welcomeOverlay.style.display = 'flex';
            
            // After animations complete (~3.5s total), hide the overlay and show the app
            setTimeout(() => {
                // Hide the welcome overlay with fade out
                welcomeOverlay.style.opacity = '0';
                welcomeOverlay.style.visibility = 'hidden';
                
                // Make the app container visible with fade in
                appContainer.classList.add('visible');
                
                // After transition completes, remove overlay from DOM
                setTimeout(() => {
                    welcomeOverlay.style.display = 'none';
                }, 800);
            }, 3500);
        };
        
        // Toggle theme (dark/light mode)
        const toggleTheme = () => {
            document.body.classList.toggle('dark-mode');
            
            // Update the theme toggle icon
            if (document.body.classList.contains('dark-mode')) {
                themeToggle.innerHTML = '<i class="fas fa-sun"></i>';
                localStorage.setItem('theme', 'dark');
            } else {
                themeToggle.innerHTML = '<i class="fas fa-moon"></i>';
                localStorage.setItem('theme', 'light');
            }
        };
        
        // Check saved theme preference
        const initTheme = () => {
            const savedTheme = localStorage.getItem('theme');
            
            if (savedTheme === 'dark') {
                document.body.classList.add('dark-mode');
                themeToggle.innerHTML = '<i class="fas fa-sun"></i>';
            } else {
                document.body.classList.remove('dark-mode');
                themeToggle.innerHTML = '<i class="fas fa-moon"></i>';
            }
        };
        
        // Initialize
        const init = () => {
            // Init theme
            initTheme();
            
            // Add event listener for theme toggle
            themeToggle.addEventListener('click', toggleTheme);
            
            // Show welcome animation
            showWelcomeAnimation();
            
            // Initialize category indicator position
            initActiveCategoryIndicator();
        };
        
        // Position the active category indicator
        const initActiveCategoryIndicator = () => {
            const activeCategory = document.querySelector('.category.active');
            const indicator = document.getElementById('activeCategoryIndicator');
            
            if (activeCategory && indicator) {
                const top = activeCategory.offsetTop;
                indicator.style.transform = `translateY(${top}px)`;
            }
        };
        
        return {
            init,
            initActiveCategoryIndicator
        };
    })();
    
    // Notification System
    const NotificationSystem = (function() {
        const notificationContainer = document.getElementById('notificationContainer');
        
        // Create a notification
        const createNotification = (message, type = 'success', duration = 3000) => {
            // Create notification element
            const notification = document.createElement('div');
            notification.className = `notification ${type}`;
            
            // Set icon based on type
            let icon = 'check-circle';
            if (type === 'warning') icon = 'exclamation-circle';
            if (type === 'error') icon = 'times-circle';
            if (type === 'info') icon = 'info-circle';
            
            // Set content
            notification.innerHTML = `
                <i class="fas fa-${icon} notification-icon"></i>
                <div class="notification-message">${message}</div>
            `;
            
            // Add to container
            notificationContainer.appendChild(notification);
            
            // Trigger animation
            setTimeout(() => {
                notification.classList.add('show');
            }, 10);
            
            // Remove after duration
            setTimeout(() => {
                notification.classList.remove('show');
                
                // Remove from DOM after animation completes
                setTimeout(() => {
                    notification.remove();
                }, 300);
            }, duration);
        };
        
        return {
            createNotification
        };
    })();
    
    // Task Manager - Handle CRUD operations for tasks
    const TaskManager = (function() {
        // Get tasks from localStorage or initialize empty array
        const getTasks = () => {
            const currentUser = AppState.getCurrentUser();
            if (!currentUser) return [];
            
            const tasks = JSON.parse(localStorage.getItem(`tasks_${currentUser.id}`)) || [];
            return tasks;
        };
        
        // Save tasks to localStorage
        const saveTasks = (tasks) => {
            const currentUser = AppState.getCurrentUser();
            if (!currentUser) return;
            
            localStorage.setItem(`tasks_${currentUser.id}`, JSON.stringify(tasks));
        };
        
        // Add a new task
        const addTask = (task) => {
            const tasks = getTasks();
            
            // Create new task object
            const newTask = {
                id: Date.now().toString(),
                title: task.title,
                description: task.description || '',
                category: task.category,
                priority: task.priority,
                dueDate: task.dueDate,
                completed: false,
                createdAt: new Date().toISOString()
            };
            
            tasks.push(newTask);
            saveTasks(tasks);
            
            // Show notification
            NotificationSystem.createNotification(`Task "${task.title}" has been added!`, 'success');
            
            return newTask;
        };
        
        // Update an existing task
        const updateTask = (taskId, updatedTask) => {
            const tasks = getTasks();
            const taskIndex = tasks.findIndex(t => t.id === taskId);
            
            if (taskIndex === -1) return null;
            
            // Update the task
            tasks[taskIndex] = {
                ...tasks[taskIndex],
                title: updatedTask.title,
                description: updatedTask.description,
                category: updatedTask.category,
                priority: updatedTask.priority,
                dueDate: updatedTask.dueDate,
                // Keep completed status and creation date
            };
            
            saveTasks(tasks);
            
            // Show notification
            NotificationSystem.createNotification(`Task "${updatedTask.title}" has been updated!`, 'info');
            
            return tasks[taskIndex];
        };
        
        // Delete a task
        const deleteTask = (taskId) => {
            const tasks = getTasks();
            const taskToDelete = tasks.find(task => task.id === taskId);
            const updatedTasks = tasks.filter(task => task.id !== taskId);
            
            saveTasks(updatedTasks);
            
            // Show notification
            if (taskToDelete) {
                NotificationSystem.createNotification(`Task "${taskToDelete.title}" has been deleted!`, 'warning');
            }
            
            return updatedTasks;
        };
        
        // Toggle task completion status
        const toggleTaskCompletion = (taskId) => {
            const tasks = getTasks();
            const taskIndex = tasks.findIndex(t => t.id === taskId);
            
            if (taskIndex === -1) return null;
            
            // Toggle the completed status
            tasks[taskIndex].completed = !tasks[taskIndex].completed;
            
            saveTasks(tasks);
            
            // Show notification based on the new status
            const task = tasks[taskIndex];
            const status = task.completed ? 'completed' : 'marked as pending';
            NotificationSystem.createNotification(`Task "${task.title}" has been ${status}!`, 'info');
            
            return task;
        };
        
        // Get tasks by category
        const getTasksByCategory = (category) => {
            const tasks = getTasks();
            
            if (category === 'all') {
                return tasks;
            }
            
            return tasks.filter(task => task.category === category);
        };
        
        // Get tasks by filter (all, pending, completed, overdue, today)
        const getTasksByFilter = (filter, tasks) => {
            const now = new Date();
            const today = new Date(now.getFullYear(), now.getMonth(), now.getDate()).toISOString().split('T')[0];
            
            switch (filter) {
                case 'all':
                    return tasks;
                case 'pending':
                    return tasks.filter(task => !task.completed);
                case 'completed':
                    return tasks.filter(task => task.completed);
                case 'overdue':
                    return tasks.filter(task => !task.completed && task.dueDate < today);
                case 'today':
                    return tasks.filter(task => task.dueDate === today);
                default:
                    return tasks;
            }
        };
        
        // Sort tasks by different criteria
        const sortTasks = (tasks, sortBy) => {
            const sortedTasks = [...tasks];
            
            switch (sortBy) {
                case 'date':
                    sortedTasks.sort((a, b) => new Date(a.dueDate) - new Date(b.dueDate));
                    break;
                case 'priority':
                    const priorityOrder = { 'high': 1, 'medium': 2, 'low': 3 };
                    sortedTasks.sort((a, b) => priorityOrder[a.priority] - priorityOrder[b.priority]);
                    break;
                case 'name':
                    sortedTasks.sort((a, b) => a.title.localeCompare(b.title));
                    break;
                default:
                    // Default to due date sorting
                    sortedTasks.sort((a, b) => new Date(a.dueDate) - new Date(b.dueDate));
            }
            
            return sortedTasks;
        };
        
        // Search tasks
        const searchTasks = (query) => {
            const tasks = getTasks();
            
            if (!query) return [];
            
            query = query.toLowerCase();
            
            return tasks.filter(task => 
                task.title.toLowerCase().includes(query) ||
                task.description.toLowerCase().includes(query) ||
                task.category.toLowerCase().includes(query)
            );
        };
        
        // Get task stats for dashboard
        const getTaskStats = () => {
            const tasks = getTasks();
            const now = new Date();
            const today = new Date(now.getFullYear(), now.getMonth(), now.getDate()).toISOString().split('T')[0];
            
            const stats = {
                total: tasks.length,
                completed: tasks.filter(task => task.completed).length,
                pending: tasks.filter(task => !task.completed).length,
                overdue: tasks.filter(task => !task.completed && task.dueDate < today).length
            };
            
            return stats;
        };
        
        // Initialize with sample tasks if none exist
        const initSampleTasks = () => {
            const tasks = getTasks();
            
            // Only add sample tasks if none exist
            if (tasks.length === 0) {
                const today = new Date();
                const tomorrow = new Date(today);
                tomorrow.setDate(tomorrow.getDate() + 1);
                const nextWeek = new Date(today);
                nextWeek.setDate(nextWeek.getDate() + 7);
                
                const sampleTasks = [
                    {
                        id: '1',
                        title: 'Finalize project report',
                        description: 'Complete the quarterly project report and send it to the manager.',
                        category: 'work',
                        priority: 'high',
                        dueDate: today.toISOString().split('T')[0],
                        completed: false,
                        createdAt: new Date().toISOString()
                    },
                    {
                        id: '2',
                        title: 'Grocery shopping',
                        description: 'Buy fruits, vegetables, milk, and bread.',
                        category: 'shopping',
                        priority: 'medium',
                        dueDate: tomorrow.toISOString().split('T')[0],
                        completed: false,
                        createdAt: new Date().toISOString()
                    },
                    {
                        id: '3',
                        title: 'Go for a run',
                        description: 'Morning jog for 30 minutes.',
                        category: 'health',
                        priority: 'low',
                        dueDate: today.toISOString().split('T')[0],
                        completed: true,
                        createdAt: new Date().toISOString()
                    },
                    {
                        id: '4',
                        title: 'Pay utility bills',
                        description: 'Pay electricity, water, and internet bills.',
                        category: 'finance',
                        priority: 'high',
                        dueDate: nextWeek.toISOString().split('T')[0],
                        completed: false,
                        createdAt: new Date().toISOString()
                    }
                ];
                
                saveTasks(sampleTasks);
                return true;
            }
            
            return false;
        };
        
        return {
            getTasks,
            addTask,
            updateTask,
            deleteTask,
            toggleTaskCompletion,
            getTasksByCategory,
            getTasksByFilter,
            sortTasks,
            searchTasks,
            getTaskStats,
            initSampleTasks
        };
    })();
    
    // Task UI Controller - Handle rendering and UI for tasks
    const TaskUIController = (function() {
        // DOM elements
        const elements = {
            taskList: document.getElementById('taskList'),
            categoryContainer: document.getElementById('categoryContainer'),
            emptyState: document.getElementById('emptyState'),
            currentCategory: document.getElementById('currentCategory'),
            categoryDescription: document.getElementById('categoryDescription'),
            dashboard: document.getElementById('dashboard'),
            taskFilters: document.getElementById('taskFilters'),
            totalTasksValue: document.getElementById('totalTasksValue'),
            completedTasksValue: document.getElementById('completedTasksValue'),
            pendingTasksValue: document.getElementById('pendingTasksValue'),
            overdueTasksValue: document.getElementById('overdueTasksValue'),
            categorySlider: document.getElementById('categorySlider'),
            categoryIndicator: document.getElementById('activeCategoryIndicator'),
            categoryCounters: document.querySelectorAll('.category .task-count'),
            taskDetailModal: document.getElementById('taskDetailModal'),
            detailTitle: document.getElementById('detailTitle'),
            detailMeta: document.getElementById('detailMeta'),
            detailDescription: document.getElementById('detailDescription'),
            detailEditBtn: document.getElementById('detailEditBtn'),
            detailClose: document.getElementById('detailClose'),
            taskModal: document.getElementById('taskModal'),
            modalTitle: document.getElementById('modalTitle'),
            modalHeader: document.getElementById('modalHeader'),
            modalClose: document.getElementById('modalClose'),
            taskForm: document.getElementById('taskForm'),
            taskId: document.getElementById('taskId'),
            taskTitle: document.getElementById('taskTitle'),
            taskDescription: document.getElementById('taskDescription'),
            taskCategory: document.getElementById('taskCategory'),
            taskPriority: document.getElementById('taskPriority'),
            taskDueDate: document.getElementById('taskDueDate'),
            categoryOptions: document.querySelectorAll('.category-option'),
            priorityOptions: document.querySelectorAll('.priority-option'),
            saveTaskBtn: document.getElementById('saveTaskBtn'),
            cancelBtn: document.getElementById('cancelBtn'),
            deleteModal: document.getElementById('deleteModal'),
            deleteTaskTitle: document.getElementById('deleteTaskTitle'),
            confirmDeleteBtn: document.getElementById('confirmDeleteBtn'),
            cancelDeleteBtn: document.getElementById('cancelDeleteBtn'),
            deleteModalClose: document.getElementById('deleteModalClose'),
            addTaskBtn: document.getElementById('addTaskBtn'),
            searchInput: document.getElementById('searchInput'),
            searchSuggestions: document.getElementById('searchSuggestions'),
            searchOverlay: document.getElementById('searchOverlay'),
            sortSelect: document.getElementById('sortSelect')
        };
        
        // Current state
        let state = {
            currentCategory: 'all',
            currentFilter: 'all',
            currentSort: 'date',
            searchQuery: '',
            editingTaskId: null,
            deletingTaskId: null,
            viewingTaskId: null,
            searchActive: false
        };
        
        // Category definitions
        const categories = {
            all: {
                icon: 'fas fa-layer-group',
                title: 'All Tasks',
                description: 'View and manage all your tasks in one place.'
            },
            work: {
                icon: 'fas fa-briefcase',
                title: 'Work Tasks',
                description: 'Professional projects, meetings, and work-related responsibilities.'
            },
            personal: {
                icon: 'fas fa-user',
                title: 'Personal Tasks',
                description: 'Personal projects, hobbies, and commitments.'
            },
            shopping: {
                icon: 'fas fa-shopping-cart',
                title: 'Shopping Tasks',
                description: 'Shopping lists, items to buy, and errands.'
            },
            health: {
                icon: 'fas fa-heartbeat',
                title: 'Health Tasks',
                description: 'Exercise routines, doctor appointments, and wellness activities.'
            },
            finance: {
                icon: 'fas fa-dollar-sign',
                title: 'Finance Tasks',
                description: 'Bills, investments, budgeting, and financial planning.'
            },
            education: {
                icon: 'fas fa-graduation-cap',
                title: 'Education Tasks',
                description: 'Courses, learning goals, and educational activities.'
            }
        };
        
        // Format date for display
        const formatDate = (dateString) => {
            const options = { weekday: 'short', year: 'numeric', month: 'short', day: 'numeric' };
            return new Date(dateString).toLocaleDateString(undefined, options);
        };
        
        // Create a task item element
        const createTaskElement = (task) => {
            const taskElement = document.createElement('div');
            taskElement.className = `task-item ${task.completed ? 'completed' : ''}`;
            taskElement.dataset.id = task.id;
            taskElement.dataset.category = task.category;
            
            // Create priority class
            const priorityClass = `priority-${task.priority}`;
            
            // Format due date for display
            const formattedDate = formatDate(task.dueDate);
            
            // Determine if task is overdue
            const now = new Date();
            const today = new Date(now.getFullYear(), now.getMonth(), now.getDate()).toISOString().split('T')[0];
            const isOverdue = !task.completed && task.dueDate < today;
            
            taskElement.innerHTML = `
                <div class="task-checkbox">
                    <input type="checkbox" ${task.completed ? 'checked' : ''} aria-label="Mark task as ${task.completed ? 'incomplete' : 'complete'}">
                </div>
                <div class="task-content">
                    <div class="task-title">${task.title}</div>
                    <div class="task-description">${task.description || 'No description provided.'}</div>
                    <div class="task-meta">
                        <div class="task-category">
                            <i class="${categories[task.category].icon}"></i> ${task.category.charAt(0).toUpperCase() + task.category.slice(1)}
                        </div>
                        <div class="task-date ${isOverdue ? 'overdue' : ''}">
                            <i class="far fa-calendar-alt"></i> ${formattedDate}
                        </div>
                        <div class="task-priority ${priorityClass}">
                            <i class="fas fa-flag"></i> ${task.priority}
                        </div>
                    </div>
                </div>
                <div class="task-actions">
                    <button class="task-action-btn edit" aria-label="Edit task">
                        <i class="fas fa-pencil-alt"></i>
                    </button>
                    <button class="task-action-btn delete" aria-label="Delete task">
                        <i class="fas fa-trash-alt"></i>
                    </button>
                </div>
            `;
            
            return taskElement;
        };
        
        // Render tasks based on current state
        const renderTasks = () => {
            // Get tasks based on current category
            let tasks = TaskManager.getTasksByCategory(state.currentCategory);
            
            // Apply filter
            tasks = TaskManager.getTasksByFilter(state.currentFilter, tasks);
            
            // Apply sorting
            tasks = TaskManager.sortTasks(tasks, state.currentSort);
            
            // Clear current task list
            elements.taskList.innerHTML = '';
            
            // Set category specific CSS class
            elements.taskList.className = 'task-list';
            if (state.currentCategory !== 'all') {
                elements.taskList.classList.add(state.currentCategory);
            }
            
            // Show empty state if no tasks
            if (tasks.length === 0) {
                let emptyStateClass = '';
                if (state.currentCategory !== 'all') {
                    emptyStateClass = state.currentCategory;
                }
                
                elements.taskList.innerHTML = `
                    <div class="empty-state ${emptyStateClass}" id="emptyState">
                        <i class="${categories[state.currentCategory].icon}" aria-hidden="true"></i>
                        <h3>No tasks found</h3>
                        <p>${state.currentFilter !== 'all' ? 'Change your filter to see more tasks' : 'Add your first task to get started'}</p>
                    </div>
                `;
                return;
            }
            
            // Render each task
            tasks.forEach(task => {
                const taskElement = createTaskElement(task);
                elements.taskList.appendChild(taskElement);
            });
            
            // Add event listeners to task elements
            addTaskEventListeners();
        };
        
        // Add event listeners to task elements
        const addTaskEventListeners = () => {
            // Get all task checkboxes
            const checkboxes = elements.taskList.querySelectorAll('.task-checkbox input');
            
            // Add event listeners to checkboxes
            checkboxes.forEach(checkbox => {
                checkbox.addEventListener('change', function() {
                    const taskId = this.closest('.task-item').dataset.id;
                    const task = TaskManager.toggleTaskCompletion(taskId);
                    
                    if (task) {
                        // Update task element state
                        const taskElement = this.closest('.task-item');
                        if (task.completed) {
                            taskElement.classList.add('completed');
                        } else {
                            taskElement.classList.remove('completed');
                        }
                        
                        // Update dashboard
                        updateDashboard();
                        
                        // Update category counters
                        updateCategoryCounts();
                    }
                });
            });
            
            // Get all edit buttons
            const editBtns = elements.taskList.querySelectorAll('.task-action-btn.edit');
            
            // Add event listeners to edit buttons
            editBtns.forEach(btn => {
                btn.addEventListener('click', function(e) {
                    e.stopPropagation();
                    const taskId = this.closest('.task-item').dataset.id;
                    openEditTaskModal(taskId);
                });
            });
            
            // Get all delete buttons
            const deleteBtns = elements.taskList.querySelectorAll('.task-action-btn.delete');
            
            // Add event listeners to delete buttons
            deleteBtns.forEach(btn => {
                btn.addEventListener('click', function(e) {
                    e.stopPropagation();
                    const taskId = this.closest('.task-item').dataset.id;
                    openDeleteConfirmation(taskId);
                });
            });
            
            // Make task items clickable to open detail view
            const taskItems = elements.taskList.querySelectorAll('.task-item');
            
            taskItems.forEach(item => {
                item.addEventListener('click', function(e) {
                    // Don't open detail view if clicking on checkbox, edit, or delete button
                    if (e.target.closest('.task-checkbox') || 
                        e.target.closest('.task-action-btn')) {
                        return;
                    }
                    
                    const taskId = this.dataset.id;
                    openTaskDetail(taskId);
                });
            });
        };
        
        // Update dashboard statistics
        const updateDashboard = () => {
            const stats = TaskManager.getTaskStats();
            
            elements.totalTasksValue.textContent = stats.total;
            elements.completedTasksValue.textContent = stats.completed;
            elements.pendingTasksValue.textContent = stats.pending;
            elements.overdueTasksValue.textContent = stats.overdue;
        };
        
        // Update category counts
        const updateCategoryCounts = () => {
            const tasks = TaskManager.getTasks();
            
            // Set all tasks count
            elements.categoryCounters[0].textContent = tasks.length;
            
            // Count tasks by category
            const categoryCounts = {
                work: 0,
                personal: 0,
                shopping: 0,
                health: 0,
                finance: 0,
                education: 0
            };
            
            tasks.forEach(task => {
                if (categoryCounts.hasOwnProperty(task.category)) {
                    categoryCounts[task.category]++;
                }
            });
            
            // Set counts on sidebar
            const categoriesList = Object.keys(categoryCounts);
            categoriesList.forEach((category, index) => {
                elements.categoryCounters[index + 1].textContent = categoryCounts[category];
            });
        };
        
        // Change active category
        const changeCategory = (category) => {
            state.currentCategory = category;
            
            // Update active category in sidebar
            const categoryElements = elements.categorySlider.querySelectorAll('.category');
            categoryElements.forEach(el => {
                if (el.dataset.category === category) {
                    el.classList.add('active');
                } else {
                    el.classList.remove('active');
                }
            });
            
            // Move the active indicator
            const activeCategory = document.querySelector(`.category[data-category="${category}"]`);
            if (activeCategory && elements.categoryIndicator) {
                const top = activeCategory.offsetTop;
                elements.categoryIndicator.style.transform = `translateY(${top}px)`;
            }
            
            // Update category title and description
            elements.currentCategory.innerHTML = `<i class="${categories[category].icon}"></i> ${categories[category].title}`;
            elements.categoryDescription.textContent = categories[category].description;
            
            // Toggle dashboard visibility
            if (category === 'all') {
                elements.dashboard.style.display = 'grid';
            } else {
                elements.dashboard.style.display = 'none';
            }
            
            // Apply transition effect
            elements.categoryContainer.classList.add('fade-out');
            
            setTimeout(() => {
                elements.categoryContainer.classList.remove('fade-out');
                elements.categoryContainer.classList.add('fade-in');
                
                // Reset filter
                state.currentFilter = 'all';
                const filterButtons = elements.taskFilters.querySelectorAll('.filter-btn');
                filterButtons.forEach(btn => {
                    if (btn.dataset.filter === 'all') {
                        btn.classList.add('active');
                    } else {
                        btn.classList.remove('active');
                    }
                });
                
                // Render tasks with new category
                renderTasks();
                
                setTimeout(() => {
                    elements.categoryContainer.classList.remove('fade-in');
                }, 300);
            }, 300);
        };
        
        // Open task detail view
        const openTaskDetail = (taskId) => {
            const tasks = TaskManager.getTasks();
            const task = tasks.find(t => t.id === taskId);
            
            if (!task) return;
            
            state.viewingTaskId = taskId;
            
            // Set task details
            elements.detailTitle.textContent = task.title;
            
            // Format due date
            const formattedDate = formatDate(task.dueDate);
            
            // Determine if task is overdue
            const now = new Date();
            const today = new Date(now.getFullYear(), now.getMonth(), now.getDate()).toISOString().split('T')[0];
            const isOverdue = !task.completed && task.dueDate < today;
            
            // Set meta information
            elements.detailMeta.innerHTML = `
                <div class="task-detail-badge category ${task.category}">
                    <i class="${categories[task.category].icon}"></i> ${task.category.charAt(0).toUpperCase() + task.category.slice(1)}
                </div>
                <div class="task-detail-badge priority ${task.priority}">
                    <i class="fas fa-flag"></i> ${task.priority.charAt(0).toUpperCase() + task.priority.slice(1)} Priority
                </div>
                <div class="task-detail-badge date ${isOverdue ? 'overdue' : ''}">
                    <i class="far fa-calendar-alt"></i> ${formattedDate}
                </div>
                <div class="task-detail-badge status ${task.completed ? '' : 'pending'}">
                    <i class="fas fa-${task.completed ? 'check-circle' : 'clock'}"></i> ${task.completed ? 'Completed' : 'Pending'}
                </div>
            `;
            
            // Set description
            elements.detailDescription.textContent = task.description || 'No description provided.';
            
            // Open modal
            elements.taskDetailModal.classList.add('active');
        };
        
        // Open edit task modal
        const openEditTaskModal = (taskId) => {
            const tasks = TaskManager.getTasks();
            const task = tasks.find(t => t.id === taskId);
            
            if (!task) return;
            
            state.editingTaskId = taskId;
            
            // Set form values
            elements.taskId.value = task.id;
            elements.taskTitle.value = task.title;
            elements.taskDescription.value = task.description || '';
            elements.taskCategory.value = task.category;
            elements.taskPriority.value = task.priority;
            elements.taskDueDate.value = task.dueDate;
            
            // Set selected category option
            elements.categoryOptions.forEach(option => {
                if (option.dataset.value === task.category) {
                    option.classList.add('selected');
                } else {
                    option.classList.remove('selected');
                }
            });
            
            // Set selected priority option
            elements.priorityOptions.forEach(option => {
                if (option.dataset.value === task.priority) {
                    option.classList.add('selected');
                } else {
                    option.classList.remove('selected');
                }
            });
            
            // Set modal header class based on category
            elements.modalHeader.className = 'modal-header';
            if (task.category !== 'all') {
                elements.modalHeader.classList.add(task.category);
            }
            
            // Update modal title
            elements.modalTitle.textContent = 'Edit Task';
            
            // Show modal
            elements.taskModal.classList.add('active');
        };
        
        // Open add task modal
        const openAddTaskModal = () => {
            state.editingTaskId = null;
            
            // Clear form
            elements.taskForm.reset();
            elements.taskId.value = '';
            
            // Set default category and priority
            elements.taskCategory.value = state.currentCategory === 'all' ? 'work' : state.currentCategory;
            elements.taskPriority.value = 'low';
            
            // Set default due date to tomorrow
            const tomorrow = new Date();
            tomorrow.setDate(tomorrow.getDate() + 1);
            elements.taskDueDate.value = tomorrow.toISOString().split('T')[0];
            
            // Set selected category option
            elements.categoryOptions.forEach(option => {
                if (option.dataset.value === elements.taskCategory.value) {
                    option.classList.add('selected');
                } else {
                    option.classList.remove('selected');
                }
            });
            
            // Set selected priority option
            elements.priorityOptions.forEach(option => {
                if (option.dataset.value === 'low') {
                    option.classList.add('selected');
                } else {
                    option.classList.remove('selected');
                }
            });
            
            // Set modal header class based on category
            elements.modalHeader.className = 'modal-header';
            if (elements.taskCategory.value !== 'all') {
                elements.modalHeader.classList.add(elements.taskCategory.value);
            }
            
            // Update modal title
            elements.modalTitle.textContent = 'Add New Task';
            
            // Show modal
            elements.taskModal.classList.add('active');
        };
        
        // Open delete confirmation modal
        const openDeleteConfirmation = (taskId) => {
            const tasks = TaskManager.getTasks();
            const task = tasks.find(t => t.id === taskId);
            
            if (!task) return;
            
            state.deletingTaskId = taskId;
            
            // Set task title in confirmation
            elements.deleteTaskTitle.textContent = task.title;
            
            // Show modal
            elements.deleteModal.classList.add('active');
        };
        
        // Handle task form submission
        const handleTaskFormSubmit = (e) => {
            e.preventDefault();
            
            // Validate form
            if (!elements.taskTitle.value.trim()) {
                elements.taskTitle.classList.add('error');
                return;
            }
            
            if (!elements.taskDueDate.value) {
                elements.taskDueDate.classList.add('error');
                return;
            }
            
            // Create task object
            const task = {
                title: elements.taskTitle.value.trim(),
                description: elements.taskDescription.value.trim(),
                category: elements.taskCategory.value,
                priority: elements.taskPriority.value,
                dueDate: elements.taskDueDate.value
            };
            
            // Check if editing or adding
            if (state.editingTaskId) {
                TaskManager.updateTask(state.editingTaskId, task);
            } else {
                TaskManager.addTask(task);
            }
            
            // Close modal
            elements.taskModal.classList.remove('active');
            
            // Update UI
            renderTasks();
            updateDashboard();
            updateCategoryCounts();
        };
        
        // Handle search input
        const handleSearchInput = () => {
            const query = elements.searchInput.value.trim();
            
            if (query.length >= 2) {
                // Show search results
                const results = TaskManager.searchTasks(query);
                
                // Clear previous results
                elements.searchSuggestions.innerHTML = '';
                
                // Show overlay and suggestions
                elements.searchOverlay.classList.add('active');
                elements.searchSuggestions.classList.add('active');
                
                state.searchActive = true;
                
                if (results.length === 0) {
                    elements.searchSuggestions.innerHTML = `
                        <div class="suggestion-item">
                            <div class="suggestion-content">
                                <div class="suggestion-title">No results found</div>
                                <div class="suggestion-category">Try a different search term</div>
                            </div>
                        </div>
                    `;
                    return;
                }
                
                // Create search results
                results.forEach(task => {
                    const resultItem = document.createElement('div');
                    resultItem.className = 'suggestion-item';
                    resultItem.dataset.id = task.id;
                    
                    const priorityClass = `priority-${task.priority}`;
                    
                    resultItem.innerHTML = `
                        <div class="suggestion-content">
                            <div class="suggestion-title">${task.title}</div>
                            <div class="suggestion-category">
                                <i class="${categories[task.category].icon}"></i> ${task.category.charAt(0).toUpperCase() + task.category.slice(1)}
                                <span class="suggestion-priority ${priorityClass}">${task.priority}</span>
                            </div>
                        </div>
                        <div class="suggestion-actions">
                            <button class="suggestion-action edit">
                                <i class="fas fa-pencil-alt"></i>
                            </button>
                            <button class="suggestion-action delete">
                                <i class="fas fa-trash-alt"></i>
                            </button>
                        </div>
                    `;
                    
                    elements.searchSuggestions.appendChild(resultItem);
                });
                
                // Add click events to search results
                const resultItems = elements.searchSuggestions.querySelectorAll('.suggestion-item');
                resultItems.forEach(item => {
                    item.addEventListener('click', function(e) {
                        if (!e.target.closest('.suggestion-action')) {
                            const taskId = this.dataset.id;
                            
                            // Close search
                            closeSearch();
                            
                            // Highlight task
                            highlightTask(taskId);
                        }
                    });
                });
                
                // Add click events to edit/delete actions
                const editActions = elements.searchSuggestions.querySelectorAll('.suggestion-action.edit');
                editActions.forEach(action => {
                    action.addEventListener('click', function(e) {
                        e.stopPropagation();
                        const taskId = this.closest('.suggestion-item').dataset.id;
                        
                        // Close search
                        closeSearch();
                        
                        // Open edit modal
                        openEditTaskModal(taskId);
                    });
                });
                
                const deleteActions = elements.searchSuggestions.querySelectorAll('.suggestion-action.delete');
                deleteActions.forEach(action => {
                    action.addEventListener('click', function(e) {
                        e.stopPropagation();
                        const taskId = this.closest('.suggestion-item').dataset.id;
                        
                        // Close search
                        closeSearch();
                        
                        // Open delete confirmation
                        openDeleteConfirmation(taskId);
                    });
                });
            } else {
                closeSearch();
            }
        };
        
        // Close search
        const closeSearch = () => {
            elements.searchOverlay.classList.remove('active');
            elements.searchSuggestions.classList.remove('active');
            state.searchActive = false;
        };
        
        // Highlight a task after search
        const highlightTask = (taskId) => {
            // Make sure the task's category is active
            const tasks = TaskManager.getTasks();
            const task = tasks.find(t => t.id === taskId);
            
            if (!task) return;
            
            // If task is in a different category, change to that category
            if (state.currentCategory !== 'all' && state.currentCategory !== task.category) {
                changeCategory(task.category);
                
                // Set a timeout to allow category change to complete
                setTimeout(() => {
                    const taskElement = document.querySelector(`.task-item[data-id="${taskId}"]`);
                    if (taskElement) {
                        // Add highlight class
                        taskElement.classList.add('search-highlight');
                        
                        // Scroll to element
                        taskElement.scrollIntoView({ behavior: 'smooth', block: 'center' });
                        
                        // Remove highlight after animation completes
                        setTimeout(() => {
                            taskElement.classList.remove('search-highlight');
                        }, 3000);
                    }
                }, 600);
            } else {
                const taskElement = document.querySelector(`.task-item[data-id="${taskId}"]`);
                if (taskElement) {
                    // Add highlight class
                    taskElement.classList.add('search-highlight');
                    
                    // Scroll to element
                    taskElement.scrollIntoView({ behavior: 'smooth', block: 'center' });
                    
                    // Remove highlight after animation completes
                    setTimeout(() => {
                        taskElement.classList.remove('search-highlight');
                    }, 3000);
                }
            }
        };
        
        // Initialize event listeners
        const initEventListeners = () => {
            // Category click events
            const categoryElements = elements.categorySlider.querySelectorAll('.category');
            categoryElements.forEach(category => {
                category.addEventListener('click', function() {
                    const categoryName = this.dataset.category;
                    changeCategory(categoryName);
                });
                
                // Keyboard accessibility
                category.addEventListener('keydown', function(e) {
                    if (e.key === 'Enter' || e.key === ' ') {
                        e.preventDefault();
                        const categoryName = this.dataset.category;
                        changeCategory(categoryName);
                    }
                });
            });
            
            // Filter click events
            const filterButtons = elements.taskFilters.querySelectorAll('.filter-btn');
            filterButtons.forEach(btn => {
                btn.addEventListener('click', function() {
                    const filter = this.dataset.filter;
                    
                    // Update active filter
                    filterButtons.forEach(b => b.classList.remove('active'));
                    this.classList.add('active');
                    
                    state.currentFilter = filter;
                    renderTasks();
                });
            });
            
            // Sort change event
            elements.sortSelect.addEventListener('change', function() {
                state.currentSort = this.value;
                renderTasks();
            });
            
            // Add task button click
            elements.addTaskBtn.addEventListener('click', openAddTaskModal);
            
            // Task form submission
            elements.taskForm.addEventListener('submit', handleTaskFormSubmit);
            
            // Cancel button click
            elements.cancelBtn.addEventListener('click', function() {
                elements.taskModal.classList.remove('active');
            });
            
            // Modal close buttons
            elements.modalClose.addEventListener('click', function() {
                elements.taskModal.classList.remove('active');
            });
            
            elements.detailClose.addEventListener('click', function() {
                elements.taskDetailModal.classList.remove('active');
            });
            
            elements.deleteModalClose.addEventListener('click', function() {
                elements.deleteModal.classList.remove('active');
            });
            
            // Edit button in task detail view
            elements.detailEditBtn.addEventListener('click', function() {
                const taskId = state.viewingTaskId;
                if (taskId) {
                    // Close detail view
                    elements.taskDetailModal.classList.remove('active');
                    
                    // Open edit modal
                    openEditTaskModal(taskId);
                }
            });
            
            // Delete confirmation buttons
            elements.confirmDeleteBtn.addEventListener('click', function() {
                const taskId = state.deletingTaskId;
                if (taskId) {
                    TaskManager.deleteTask(taskId);
                    
                    // Close modal
                    elements.deleteModal.classList.remove('active');
                    
                    // Update UI
                    renderTasks();
                    updateDashboard();
                    updateCategoryCounts();
                }
            });
            
            elements.cancelDeleteBtn.addEventListener('click', function() {
                elements.deleteModal.classList.remove('active');
            });
            
            // Category option selection in form
            elements.categoryOptions.forEach(option => {
                option.addEventListener('click', function() {
                    const category = this.dataset.value;
                    
                    // Update hidden input
                    elements.taskCategory.value = category;
                    
                    // Update selected class
                    elements.categoryOptions.forEach(opt => opt.classList.remove('selected'));
                    this.classList.add('selected');
                    
                    // Update modal header
                    elements.modalHeader.className = 'modal-header';
                    elements.modalHeader.classList.add(category);
                });
            });
            
            // Priority option selection in form
            elements.priorityOptions.forEach(option => {
                option.addEventListener('click', function() {
                    const priority = this.dataset.value;
                    
                    // Update hidden input
                    elements.taskPriority.value = priority;
                    
                    // Update selected class
                    elements.priorityOptions.forEach(opt => opt.classList.remove('selected'));
                    this.classList.add('selected');
                });
            });
            
            // Search input event
            elements.searchInput.addEventListener('input', handleSearchInput);
            
            // Search overlay click (to close search)
            elements.searchOverlay.addEventListener('click', closeSearch);
            
            // Pressing Escape key closes search
            document.addEventListener('keydown', function(e) {
                if (e.key === 'Escape' && state.searchActive) {
                    closeSearch();
                }
            });
        };
        
        // Initialize
        const init = () => {
            // Initialize sample tasks if needed
            const samplesAdded = TaskManager.initSampleTasks();
            
            // Initialize event listeners
            initEventListeners();
            
            // Render initial tasks
            renderTasks();
            
            // Update dashboard
            updateDashboard();
            
            // Update category counts
            updateCategoryCounts();
            
            // Show welcome notification if sample tasks were added
            if (samplesAdded) {
                setTimeout(() => {
                    NotificationSystem.createNotification('Welcome to Tasklytic! Sample tasks have been added to help you get started.', 'info', 5000);
                }, 4000);
            }
        };
        
        return {
            init,
            renderTasks
        };
    })();
    
    // Initialize the application
    UIController.init();
    TaskUIController.init();
});
</script>
</body>
</html>
