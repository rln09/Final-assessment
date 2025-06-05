Local Component State:
Used useState for stores data, loading states, filters, and user location
Kept state colocated with the component since this is a self-contained feature

Derived State:
Used useMemo for sorted stores to avoid recalculating on every render
Filtered stores are recalculated only when dependencies change

Error Handling:
Used React Error Boundary via useErrorBoundary hook
Local error state for API errors with fallback UI
Graceful degradation when geolocation isn't available

Performance Optimizations:
Memoization with useMemo and useCallback to prevent unnecessary recalculations
Efficient filtering only when dependencies change
Loading states to prevent layout shifts

Component Lifecycle and usage of hooks
Mounting:
use Effect with empty dependency array fetches initial data
Another useEffect gets user location

Updates:
useEffect watches for filter changes to update filtered stores
useMemo optimizes sorting calculation

Unmounting:
Cleanup functions in useEffect would cancel pending requests if needed

Hooks Usage:
useState for all local state management
useEffect for side effects
useMemo for expensive calculations
useCallback for stable function references
useErrorBoundary for error handling

