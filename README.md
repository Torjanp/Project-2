using System;
using System.Drawing;
using System.Windows.Forms;
using System.CodeDom.Compiler;

namespace csharp_compiler_own
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            CodeDomProvider cDProvider = CodeDomProvider.CreateProvider("CSharp");
            ICodeCompiler iCodeCompi = cDProvider.CreateCompiler();
            //place holder output
            string Output = @"C:\output.exe";
            Button buttonObject = (Button)sender;

            textBox2.Text = "";
            System.CodeDom.Compiler.CompilerParameters parameters = new CompilerParameters();
            parameters.GenerateExecutable = true;
            parameters.CompilerOptions = "/t:winexe";
            parameters.OutputAssembly = Output;
            //all refereces in a source code need to be declared here
            parameters.ReferencedAssemblies.Add("System.dll");
            parameters.ReferencedAssemblies.Add("System.Data.dll");
            parameters.ReferencedAssemblies.Add("System.Windows.Forms.dll");
            parameters.ReferencedAssemblies.Add("System.Drawing.dll");
            //place holder paths for slimDX
            parameters.ReferencedAssemblies.Add(@"C:\Program Files (x86)\SlimDX SDK (January 2012)\Bin\net40\x86\SlimDX.dll");
            CompilerResults results = iCodeCompi.CompileAssemblyFromSource(parameters, textBox1.Text);

            if (results.Errors.Count > 0)
            {
                textBox2.ForeColor = Color.Red;
                foreach (CompilerError CompErr in results.Errors)
                {
                    textBox2.Text = textBox2.Text +
                                "Line number " + CompErr.Line +
                                ", Error Number: " + CompErr.ErrorNumber +
                                ", '" + CompErr.ErrorText + ";" +
                                Environment.NewLine + Environment.NewLine;
                }
            }
            else
            {
                textBox2.ForeColor = Color.Blue;
                textBox2.Text = "done";
            }
        }
    }
}
