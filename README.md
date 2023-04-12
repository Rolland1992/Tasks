using System;
using Xunit;

namespace QuadraticEquation.Tests
{
    public class QuadraticEquationSolverTests
    {
        [Fact]
        public void Solve_WhenNoRealRoots_ShouldReturnNull()
        {
            // Arrange
            double a = 1;
            double b = 2;
            double c = 3;

            // Act
            Tuple<double, double> result = QuadraticEquationSolver.Solve(a, b, c);

            // Assert
            Assert.Null(result);
        }

        [Fact]
        public void Solve_WhenOneRealRoot_ShouldReturnTupleWithSameValue()
        {
            // Arrange[Git task.odt](https://github.com/Rolland1992/Tasks/files/11216392/Git.task.odt)

            double a = 1;
            double b = -2;
            double c = 1;

            // Act
            Tuple<double, double> result = QuadraticEquationSolver.Solve(a, b, c);

            // Assert
            Assert.NotNull(result);
            Assert.Equal(-1, result.Item1);
            Assert.Equal(-1, result.Item2);
        }

        [Fact]
        public void Solve_WhenTwoRealRoots_ShouldReturnTupleWithDifferentValues()
        {
            // Arrange
            double a = 1;
            double b = -3;
            double c = 2;

            // Act
            Tuple<double, double> result = QuadraticEquationSolver.Solve(a, b, c);

            // Assert
            Assert.NotNull(result);
            Assert.Equal(1, result.Item1);
            Assert.Equal(2, result.Item2);
        }
    }
}
