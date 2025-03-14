# Contributing to CCO-VIBE

First off, thank you for considering contributing to CCO-VIBE! It's people like you that make CCO-VIBE such a great tool.

## Code of Conduct

This project and everyone participating in it is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check the issue list as you might find out that you don't need to create one. When you are creating a bug report, please include as many details as possible:

* Use a clear and descriptive title
* Describe the exact steps which reproduce the problem
* Provide specific examples to demonstrate the steps
* Describe the behavior you observed after following the steps
* Explain which behavior you expected to see instead and why
* Include screenshots and animated GIFs if possible

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, please provide the following information:

* Use a clear and descriptive title
* Provide a step-by-step description of the suggested enhancement
* Provide specific examples to demonstrate the steps
* Describe the current behavior and explain which behavior you expected to see instead
* Explain why this enhancement would be useful

### Pull Requests

* Fill in the required template
* Do not include issue numbers in the PR title
* Follow the TypeScript styleguide
* Include screenshots and animated GIFs in your pull request whenever possible
* End files with a newline
* Avoid platform-dependent code

## Development Process

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Setup Development Environment

```bash
# Clone your fork
git clone https://github.com/your-username/cco-vibe.git

# Navigate to the project directory
cd cco-vibe

# Install dependencies
npm install

# Start development server
npm run dev
```

### Style Guide

#### TypeScript

* Use TypeScript for all new code
* Define explicit types for all variables and function parameters
* Use interfaces over types when possible
* Follow the existing code style

```typescript
// Good
interface UserProps {
  name: string;
  age: number;
}

const User: React.FC<UserProps> = ({ name, age }) => {
  return <div>{name} ({age})</div>;
};

// Bad
type UserProps = {
  name: string;
  age: number;
}

const User = (props: UserProps) => {
  return <div>{props.name} ({props.age})</div>;
};
```

#### React Components

* Use functional components with hooks
* Keep components small and focused
* Use proper prop types
* Implement error boundaries where necessary

```typescript
// Good
const Button: React.FC<ButtonProps> = ({ 
  label, 
  onClick, 
  variant = 'primary' 
}) => {
  return (
    <button 
      className={`btn btn-${variant}`}
      onClick={onClick}
    >
      {label}
    </button>
  );
};

// Bad
function Button(props) {
  return <button onClick={props.onClick}>{props.label}</button>;
}
```

### Testing

* Write tests for all new features
* Maintain existing tests
* Aim for high test coverage
* Use meaningful test descriptions

```typescript
describe('Button', () => {
  it('should render with default variant', () => {
    const { getByText } = render(<Button label="Click me" onClick={() => {}} />);
    expect(getByText('Click me')).toHaveClass('btn btn-primary');
  });

  it('should call onClick when clicked', () => {
    const handleClick = jest.fn();
    const { getByText } = render(
      <Button label="Click me" onClick={handleClick} />
    );
    fireEvent.click(getByText('Click me'));
    expect(handleClick).toHaveBeenCalledTimes(1);
  });
});
```

### Documentation

* Update documentation with any changes
* Write clear and concise commit messages
* Include JSDoc comments for functions and components
* Keep README.md up to date

```typescript
/**
 * Button component that follows the design system
 * @param {ButtonProps} props - The component props
 * @returns {React.ReactElement} The rendered button
 */
const Button: React.FC<ButtonProps> = ({ 
  label, 
  onClick, 
  variant = 'primary' 
}) => {
  // ...
};
```

## Community

* Join our [Discord server](https://discord.gg/cco-vibe)
* Follow us on [Twitter](https://twitter.com/ccovibe)
* Read our [blog](https://blog.cco-vibe.com)

## Questions?

Feel free to contact the project maintainers if you have any questions or need help getting started.

## License

By contributing to CCO-VIBE, you agree that your contributions will be licensed under its MIT license. 